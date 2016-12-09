---
layout: post
title:  "How to save an image to iOS photos library"
date:   2016-12-09
categories: snippets
image: /images/save-image.png
author: Dave Coffin
tags: 
    - ios
    - photos
    - images
shortdesc: 	This was adapted from another user's code, but moved to be in your photos view model rather than editing the image-source module itself.
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/save-image.png">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">JavaScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-javascript">
        <code>
 viewModel.saveToAlbum = function(instance, format, quality) {
    var res = false;
    if (!instance) {
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
    UIImageWriteToSavedPhotosAlbum(instance, completionTarget,
        &#x22;thisImage:hasBeenSavedInPhotoAlbumWithError:usingContextInfo:&#x22;,
        null);
    return result;
};

// and in your view js code
photosModel.saveToAlbum(imageSource.ios, enums.ImageFormat.jpeg);
        </code>
    </pre>
   </p>
</div>
</li>

</ul>
