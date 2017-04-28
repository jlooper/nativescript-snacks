---
layout: post
title:  "Save an image to a device's photo library"
date:   2017-04-27
categories: snippets
image: /images/saved.png
author: Dave Coffin
tags: 
    - image
    - save
    - ios
shortdesc: 	How to save an image to the device's photo library on iOS and Android.
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/saved.png">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">JavaScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-javascript">
        <code>
viewModel.saveToAlbum = function(imageSource, format, quality, callBack) {
    if (app.ios) {
        var res = false;
        if (!imageSource) {
            return res;
        }
        var result = true;
        var CompletionTarget = NSObject.extend({
            &#x22;thisImage:hasBeenSavedInPhotoAlbumWithError:usingContextInfo:&#x22;: function(
                image, error, context) {
                if (error) {
                    result = false;
                }
            }
        }, {
            exposedMethods: {
                &#x22;thisImage:hasBeenSavedInPhotoAlbumWithError:usingContextInfo:&#x22;: {
                    returns: interop.types.void,
                    params: [UIImage, NSError, interop.Pointer]
                }
            }
        });
        var completionTarget = CompletionTarget.new();
        UIImageWriteToSavedPhotosAlbum(imageSource.ios, completionTarget,
            &#x22;thisImage:hasBeenSavedInPhotoAlbumWithError:usingContextInfo:&#x22;,
            null);
            if (callBack) callBack();
        return result;
    } else {
        function broadCast(imageFile) {

            var mediaScanIntent = new android.content.Intent(android.content.Intent.ACTION_MEDIA_SCANNER_SCAN_FILE);
            var contentUri = android.net.Uri.fromFile(imageFile);
            mediaScanIntent.setData(contentUri);
            app.android.foregroundActivity.sendBroadcast(mediaScanIntent);
            if (callBack) callBack();
            return result;
        }

        var folderPath = android.os.Environment.getExternalStoragePublicDirectory(android.os.Environment.DIRECTORY_PICTURES).toString();
        var fileName = &#x27;img_&#x27; + new Date().getTime() + &#x27;.jpg&#x27;;
        var path = fsModule.path.join(folderPath, fileName);
        var exists = fsModule.File.exists(path);
        if (!exists) {
            var saved = imageSource.saveToFile(path, enums.ImageFormat.jpeg);
            if (saved) broadCast(new java.io.File(path));
        }        
    }
};
        </code>
    </pre>
   </p>
</div>
</li>
</ul>
