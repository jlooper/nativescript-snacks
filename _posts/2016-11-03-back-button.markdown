---
layout: post
title:  "Managing the Android back button"
date:   2016-11-03
categories: snippets
image: /images/android.png
author: Dinh Le
tags: 
    - android
    - button
    - back button
shortdesc: How to enable double pressing on the Android physical button to dismiss and kill the app
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/android.png">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">JavaScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-html">
        <code>
var frameModule = require(&#x22;ui/frame&#x22;);
var application = require(&#x22;application&#x22;)

var activity = application.android.startActivity ||
        application_1.android.foregroundActivity ||
        frameModule.topmost().android.currentActivity ||
        frameModule.topmost().android.activity;
var lastPress;

activity.onBackPressed = function() {
    var timeDelay = 500
    if (lastPress + timeDelay &#x3E; java.lang.System.currentTimeMillis()) {
        var startMain = new android.content.Intent(android.content.Intent.ACTION_MAIN);
        startMain.addCategory(android.content.Intent.CATEGORY_HOME);
        startMain.setFlags(android.content.Intent.FLAG_ACTIVITY_NEW_TASK);
        activity.startActivity(startMain);

        // If you want to kill the app totally, use these codes instead of above
        // activity.finish();
        // java.lang.System.exit(0);

    } else {
        frameModule.topmost().goBack();
    }
    lastPress = java.lang.System.currentTimeMillis();
}
</code></pre>
   </p>
</div>
</li>
</ul>
