---
layout: post
title:  "Chat Bubbles with Nativescript"
date:   2016-09-01
categories: snippets
image: /images/chat.png
author: Dave Coffin
tags: 
    - chat
    - layouts
    - bubbles
shortdesc: 	Dave shows us how to make a simple chat UI with an iMessage type interface
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/chat.png">
    </div>
</li>
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;ListView.itemTemplate&#x3E;
    &#x3C;StackLayout id=&#x22;{{id}}&#x22;&#x3E;

        &#x3C;StackLayout  visibility=&#x22;{{is_me ? &#x27;collapsed&#x27; : &#x27;visible&#x27;}}&#x22;&#x3E;
            &#x3C;GridLayout width=&#x22;100%&#x22; columns=&#x22;*&#x22; rows=&#x22;auto, 20&#x22; class=&#x22;msg them&#x22;&#x3E;
                &#x3C;StackLayout orientation=&#x22;horizontal&#x22;&#x3E;
                    &#x3C;Image class=&#x22;authorimg&#x22; width=&#x22;30&#x22; height=&#x22;30&#x22; stretch=&#x22;aspectFill&#x22; verticalAlignment=&#x22;top&#x22; src=&#x22;{{user.profile_photo ? user.profile_photo.sizes.tiny_square : &#x27;&#x27;}}&#x22; /&#x3E;
                    &#x3C;Label text=&#x22;{{message}}&#x22; textWrap=&#x22;true&#x22; verticalAlignment=&#x22;top&#x22; class=&#x22;msg_text&#x22;/&#x3E;                                
                &#x3C;/StackLayout&#x3E;

                &#x3C;Label class=&#x22;msg_timestamp&#x22; text=&#x22;{{author}}&#x22; verticalAlignment=&#x22;top&#x22; row=&#x22;1&#x22; colSpan=&#x22;2&#x22; /&#x3E;
            &#x3C;/GridLayout&#x3E;
        &#x3C;/StackLayout&#x3E;

        &#x3C;StackLayout  visibility=&#x22;{{is_me ? &#x27;visible&#x27; : &#x27;collapsed&#x27;}}&#x22;&#x3E;
            &#x3C;GridLayout columns=&#x22;*&#x22; rows=&#x22;auto, 40&#x22; class=&#x22;msg me&#x22;&#x3E;
                &#x3C;StackLayout orientation=&#x22;horizontal&#x22; horizontalAlignment=&#x22;right&#x22;&#x3E;
                    &#x3C;Label text=&#x22;{{message}}&#x22; class=&#x22;msg_text&#x22; textWrap=&#x22;true&#x22; verticalAlignment=&#x22;top&#x22; /&#x3E;
                    &#x3C;Image class=&#x22;authorimg&#x22; stretch=&#x22;aspectFill&#x22; height=&#x22;30&#x22; width=&#x22;30&#x22; verticalAlignment=&#x22;top&#x22; src=&#x22;{{user.profile_photo ? user.profile_photo.sizes.tiny_square : &#x27;&#x27;}}&#x22; col=&#x22;1&#x22; /&#x3E;
                &#x3C;/StackLayout&#x3E;
                &#x3C;Label class=&#x22;msg_timestamp&#x22; text=&#x22;{{author}}&#x22; verticalAlignment=&#x22;top&#x22; row=&#x22;1&#x22; /&#x3E;
            &#x3C;/GridLayout&#x3E;
        &#x3C;/StackLayout&#x3E;

    &#x3C;/StackLayout&#x3E;
&#x3C;/ListView.itemTemplate&#x3E;
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
.msg {
    font-size: 14px;
    margin-top: 5px;
    margin-bottom: 20;
}

.me .msg_text {
    background-color: #30A9FF;
    color: white;
    padding: 8px;
    margin-left: 40px;
    border-radius: 15;
    
}

.them .msg_text {
    background-color: #e0e0e0;
    color: #333;
    padding: 7px;
    border-radius: 15;
    margin-right: 40px;
}

.authorimg {
    margin: 0px 5px 5px 5px;
    width: 30;
    height: 30;
    border-radius: 15;
}

.them .msg_timestamp {
    color: gray;
    font-size: 11px;
    margin-left: 40px;
}

.me .msg_timestamp {
    color: gray;
    font-size: 11px;
    margin-right: 40px;
    text-align: right;
}

   </code>
  </pre>
</div>
</li>
<li>
    <input type="radio" name="tabs" id="tab4" />
    <label for="tab4">Notes</label>
    <div id="tab-content4" class="tab-content">
      <p>
It took me forever to figure this one out, but with a little help from my friends (http://stackoverflow.com/questions/39236005/nativescript-make-label-span-width-of-its-content-then-wrap-at-a-max-width), I now have a beautiful chat UI. My struggle was figuring out a way to make a Label span only the width of its textual content, but wrap at the bounds of the UI. Turns out a StackLayout with orientation="horizontal" is the way to achieve this. And horizontalAlign="right" does the job for the blue (me) bubbles. Enjoy! 
   </p>
</div>
</li>
</ul>
