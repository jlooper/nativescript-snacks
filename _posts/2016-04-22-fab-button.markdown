---
layout: post
title:  "Material Design FAB Speed Dial"
date:   2016-04-22
categories: snippets
author: Brad Martin
image: /images/fab-button.gif
tags: 
    - material design
    - animation
shortdesc: Brad Martin's FAB button. 
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/fab-button.gif">
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
 &#x3C;Page xmlns=&#x22;http://schemas.nativescript.org/tns.xsd&#x22; loaded=&#x22;pageLoaded&#x22;
      xmlns:FAB=&#x22;nativescript-floatingactionbutton&#x22;
       xmlns:Gif=&#x22;nativescript-gif&#x22;&#x3E;
    &#x3C;Page.actionBar&#x3E;
        &#x3C;ActionBar title=&#x22;Native FAB&#x22; backgroundColor=&#x22;#3F51B5&#x22; color=&#x22;#fff&#x22; /&#x3E;
    &#x3C;/Page.actionBar&#x3E;
    &#x3C;grid-layout rows=&#x22;auto,*&#x22;&#x3E;
        &#x3C;list-view id=&#x22;userList&#x22; row=&#x22;1&#x22; items=&#x22;{{ users }}&#x22;&#x3E;
            &#x3C;list-view.itemTemplate&#x3E;
                &#x3C;label text=&#x22;{{ name }}&#x22; textWrap=&#x22;true&#x22; fontSize=&#x22;15&#x22; margin=&#x22;20&#x22; /&#x3E;
            &#x3C;/list-view.itemTemplate&#x3E;
        &#x3C;/list-view&#x3E;
        
 &#x3C;image tap=&#x22;doThis&#x22; id=&#x22;btna&#x22; src=&#x22;~/pics/brad.PNG&#x22; class=&#x22;speed-button&#x22; row=&#x22;1&#x22; /&#x3E;
 &#x3C;image tap=&#x22;doThis&#x22; id=&#x22;btnb&#x22; src=&#x22;~/pics/walker.jpeg&#x22; class=&#x22;speed-button&#x22; row=&#x22;1&#x22; /&#x3E;
 &#x3C;image tap=&#x22;doThis&#x22; id=&#x22;btnc&#x22; src=&#x22;~/pics/nraboy.png&#x22; class=&#x22;speed-button&#x22; row=&#x22;1&#x22; /&#x3E;
 &#x3C;image tap=&#x22;doThis&#x22; id=&#x22;btnd&#x22; src=&#x22;~/pics/jenlooper.jpeg&#x22; class=&#x22;speed-button&#x22; row=&#x22;1&#x22; /&#x3E;
 &#x3C;image tap=&#x22;doThis&#x22; id=&#x22;btne&#x22; src=&#x22;~/pics/burke.jpg&#x22; class=&#x22;speed-button&#x22; row=&#x22;1&#x22; /&#x3E;
 &#x3C;Gif:Gif tap=&#x22;doThis&#x22; id=&#x22;btnf&#x22; src=&#x22;~/pics/june.gif&#x22; class=&#x22;speed-button&#x22; row=&#x22;1&#x22; /&#x3E;        
            &#x3C;FAB:fab
                row=&#x22;1&#x22;
                icon=&#x22;res://icon&#x22;
                tap=&#x22;fabTap&#x22;
                rippleColor=&#x22;#fff&#x22;
                class=&#x22;fab-button&#x22;  /&#x3E; 
                
    &#x3C;/grid-layout&#x3E;
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
 .fab-button {
    height: 70;
    margin: 15;
    background-color: #ff4081; 
    horizontal-align: right; 
    vertical-align: bottom; 
}

.speed-button {
    height: 40;
    width:40;
    margin: 22;
    background-color: transparent;
    color: #fff;
    opacity: 0;
    border-radius: 20;
    horizontal-align: right; 
    vertical-align: bottom; 
}

        </code>
      </pre>
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab4" />
    <label for="tab4">JavaScript</label>
    <div id="tab-content4" class="tab-content">
      <pre class="language-javascript">
        <code>var isFabOpen = false;

function fabTap(args) {
    var fab = args.object;
    var button = page.getViewById('btna');
    var button2 = page.getViewById('btnb');
    var button3 = page.getViewById('btnc');
    var button4 = page.getViewById('btnd');
    var button5 = page.getViewById('btne');
    var button6 = page.getViewById('btnf');


    if (isFabOpen === true) {

        var animations = [
            { target: fab, rotate: 0, duration: 400, delay: 0 },
            { target: button, translate: { x: 0, y: 0 }, opacity: 0, duration: 400, delay: 0 },
            { target: button2, translate: { x: 0, y: 0 }, opacity: 0, duration: 440, delay: 0 },
            { target: button3, translate: { x: 0, y: 0 }, opacity: 0, duration: 440, delay: 0 },
            { target: button4, translate: { x: 0, y: 0 }, opacity: 0, duration: 440, delay: 0 },
            { target: button5, translate: { x: 0, y: 0 }, opacity: 0, duration: 440, delay: 0 },
            { target: button6, translate: { x: 0, y: 0 }, opacity: 0, duration: 440, delay: 0 }

        ];
        var a = new animation.Animation(animations);
        a.play()
            .then(function () {
                //console.log("Animations finished");
                isFabOpen = false;
            })
            .catch(function (e) {
                console.log(e.message);
            });

    } else {

        var animations = [
            { target: fab, rotate: 45, duration: 400, delay: 0 },
            { target: button, translate: { x: 0, y: -54 }, opacity: 1, duration: 400, delay: 0 },
            { target: button2, translate: { x: 0, y: -100 }, opacity: 1, duration: 440, delay: 0 },
            { target: button3, translate: { x: 0, y: -154 }, opacity: 1, duration: 440, delay: 0 },
            { target: button4, translate: { x: 0, y: -200 }, opacity: 1, duration: 440, delay: 0 },
            { target: button5, translate: { x: 0, y: -254 }, opacity: 1, duration: 440, delay: 0 },
            { target: button6, translate: { x: 0, y: -300 }, opacity: 1, duration: 440, delay: 0 }
        ];
        var a = new animation.Animation(animations);
        a.play()
            .then(function () {
                //console.log("Animations finished");
                isFabOpen = true;
            })
            .catch(function (e) {
                console.log(e.message);
            });
    }
}
exports.fabTap = fabTap;
</code>
      </pre>
    </div>
  </li>
</ul>
