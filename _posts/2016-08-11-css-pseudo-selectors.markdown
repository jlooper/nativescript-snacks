---
layout: post
title:  "CSS button pressed selector"
date:   2016-08-11
categories: snippets
image: /images/button-pressed.gif
author: Nathanael Anderson
tags: 
    - css
    - selectors
    - button
    - pressed
shortdesc: 	How to use the brand new button pressed ability to highlight it
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/button-pressed.gif">
    </div>
</li>
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;Page&#x3E;
  &#x3C;StackLayout&#x3E;   
    &#x3C;Button text=&#x22;TAP&#x22;&#x3E;&#x3C;/Button&#x3E;
  &#x3C;/StackLayout&#x3E;
&#x3C;/Page&#x3E;	
		</code>
  </pre>
</div>
</li>     
<li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">CSS</label>
    <div id="tab-content3" class="tab-content">
      <pre class="language-javascript">
  <code>
Button:highlighting {
   background-color:cyan;
}
   </code>
  </pre>
</div>
</li>
</ul>
