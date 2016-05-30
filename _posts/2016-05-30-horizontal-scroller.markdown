---
layout: post
title:  "Horizontal Scrolling Section"
date:   2016-05-30
categories: snippets
image: /images/horizontal-scroll.gif
author: Brad Martin
tags: 
    - design
    - menu
    - UI
    - scrolling
    - sliding
    - XML
    - slides
shortdesc: Brad creates a horizontal scrolling section, great for lists and menus.
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/horizontal-scroll.gif">
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;Page xmlns=&#x22;http://schemas.nativescript.org/tns.xsd&#x22; navigatingTo=&#x22;onNavigatingTo&#x22;&#x3E;
    &#x3C;ActionBar title=&#x22;Horizontal Scrolling&#x22; backgroundColor=&#x22;#3F51B5&#x22; color=&#x22;#fff&#x22; /&#x3E;
    &#x3C;StackLayout padding=&#x22;10&#x22;&#x3E;
      
      
      &#x3C;!-- This is the IMPORTANT part --&#x3E;
        &#x3C;ScrollView orientation=&#x22;horizontal&#x22;&#x3E;
            &#x3C;StackLayout orientation=&#x22;horizontal&#x22; class=&#x22;scroll-menu&#x22;&#x3E;
                &#x3C;GridLayout rows=&#x22;*, auto&#x22; columns=&#x22;*, auto&#x22; class=&#x22;scroll-pane&#x22;&#x3E;
                    &#x3C;Button row=&#x22;1&#x22; col=&#x22;1&#x22; text=&#x22;Button&#x22; horizontalAlignment=&#x22;right&#x22; /&#x3E;
                &#x3C;/GridLayout&#x3E;
                &#x3C;GridLayout rows=&#x22;*, auto&#x22; columns=&#x22;*, auto&#x22; class=&#x22;scroll-pane&#x22;&#x3E;
                    &#x3C;Button row=&#x22;1&#x22; col=&#x22;1&#x22; text=&#x22;Button&#x22; horizontalAlignment=&#x22;right&#x22; /&#x3E;
                &#x3C;/GridLayout&#x3E;
                &#x3C;GridLayout rows=&#x22;*, auto&#x22; columns=&#x22;*, auto&#x22; class=&#x22;scroll-pane&#x22;&#x3E;
                    &#x3C;Button row=&#x22;1&#x22; col=&#x22;1&#x22; text=&#x22;Button&#x22; horizontalAlignment=&#x22;right&#x22; /&#x3E;
                &#x3C;/GridLayout&#x3E;
                &#x3C;GridLayout rows=&#x22;*, auto&#x22; columns=&#x22;*, auto&#x22; class=&#x22;scroll-pane&#x22;&#x3E;
                    &#x3C;Button row=&#x22;1&#x22; col=&#x22;1&#x22; text=&#x22;Button&#x22; horizontalAlignment=&#x22;right&#x22; /&#x3E;
                &#x3C;/GridLayout&#x3E;
                &#x3C;GridLayout rows=&#x22;*, auto&#x22; columns=&#x22;*, auto&#x22; class=&#x22;scroll-pane&#x22;&#x3E;
                    &#x3C;Button row=&#x22;1&#x22; col=&#x22;1&#x22; text=&#x22;Button&#x22; horizontalAlignment=&#x22;right&#x22; /&#x3E;
                &#x3C;/GridLayout&#x3E;
            &#x3C;/StackLayout&#x3E;
        &#x3C;/ScrollView&#x3E;
      
      
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
      <pre class="language-css">
        <code>
.scroll-menu {
    height: 220;
}

.scroll-pane {
    background-color: #FF4081;
    width: 240;
    height: 220d;
    margin: 10;
}
		</code>
      </pre>
    </div>
  </li>
  
    
</ul>
