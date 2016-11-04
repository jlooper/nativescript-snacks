---
layout: post
title:  "Angular animations for your FAB button"
date:   2016-11-04
categories: snippets
type: ng
image: /images/fab-animated.gif
author: Jen Looper
tags: 
    - animation
    - angular
    - FAB button
shortdesc: 	If you prefer Angular animations to animate your FAB button group (over keyframes or the animation library), try this!
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/fab-animated.gif">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">TypeScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-html">
        <code>
  @BaseComponent({
  moduleId: module.id,
  selector: &#x27;sd-home&#x27;,
  templateUrl: &#x27;home.component.html&#x27;,
  styleUrls: [&#x27;home.css&#x27;],
  animations: [
        trigger(&#x27;state&#x27;, [
            state(&#x27;active&#x27;, style({ transform: &#x27;rotate(45)&#x27; })),
            state(&#x27;inactive&#x27;, style({ transform: &#x27;rotate(0)&#x27; })),
            transition(&#x27;inactivebtn =&#x3E; activebtna&#x27;, [
                animate(&#x27;280ms ease-in&#x27;, keyframes([
                    style({opacity: 1, transform: &#x27;translateY(0)&#x27;}),
                    style({opacity: 1, transform: &#x27;translateX(70)&#x27;})                
                ]))
            ]),
            transition(&#x27;inactivebtn =&#x3E; activebtnb&#x27;, [
                 animate(&#x27;280ms ease-in&#x27;, keyframes([
                    style({opacity: 1, transform: &#x27;translateX(0)&#x27;}),
                    style({opacity: 1, transform: &#x27;translateY(-80)&#x27;})
                ]))
            ]),
            transition(&#x27;inactivebtn =&#x3E; activebtnc&#x27;, [
                 animate(&#x27;280ms ease-in&#x27;, keyframes([
                    style({opacity: 1, transform: &#x27;translateY(0)&#x27;}),
                    style({opacity: 1, transform: &#x27;translateX(-70)&#x27;}),
                    
                ]))
            ]),
            transition(&#x27;activebtna =&#x3E; inactivebtn&#x27;, [
               animate(&#x27;280ms ease-out&#x27;, keyframes([
                    style({opacity: 0, transform: &#x27;translateX(0)&#x27;}),
                    style({opacity: 0, transform: &#x27;translateY(0)&#x27;})
                ]))
            ]),
            transition(&#x27;activebtnb =&#x3E; inactivebtn&#x27;, [
                 animate(&#x27;280ms ease-out&#x27;, keyframes([
                    style({opacity: 0, transform: &#x27;translateX(0)&#x27;}),
                    style({opacity: 0, transform: &#x27;translateY(0)&#x27;})
                ]))
            ]),
            transition(&#x27;activebtnc =&#x3E; inactivebtn&#x27;, [
                 animate(&#x27;280ms ease-out&#x27;, keyframes([
                    style({opacity: 0, transform: &#x27;translateX(0)&#x27;}),
                    style({opacity: 0, transform: &#x27;translateY(0)&#x27;})
                ]))
            ])
        ]) 
    ]  
})
</code></pre>
   </p>
</div>
</li>
<li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">CSS</label>
    <div id="tab-content3" class="tab-content">
      <p>
      <pre class="language-html">
        <code>
  /*FAB button*/

.fa {
  font-family: FontAwesome, fontawesome-webfont;
  font-size:20;
}
.speed-button {
    height: 50;
    width: 50;
    font-size: 20;
    text-align: center;
    color: #fff;
    border-radius: 25;
    horizontal-align: center;
    vertical-align: bottom;
}
.btnb {
  background-color: #6DE9C0; 
}
.btna {
  background-color: #F2B208; 
}
.btne {
  background-color: #F13030; 
}
.fab-button {
    height: 70;
    width: 70;
    margin: 10;
    background-color: #088FFC;
    horizontal-align: center;
    vertical-align: bottom;
}
.action-btn{
  background-color: #1598F6;    
  margin-top: 5;
  border-radius:2;
}
</code></pre>
   </p>
</div>
<li>
    <input type="radio" name="tabs" id="tab4" />
    <label for="tab4">XML</label>
    <div id="tab-content4" class="tab-content">
      <p>
      <pre class="language-html">
        <code>
  &#x3C;Button row=&#x22;1&#x22; #btna (tap)=&#x22;addStudent()&#x22; [@state]=&#x22; isOpen ? &#x27;activebtna&#x27; : &#x27;inactivebtn&#x27; &#x22; [text]=&#x22;&#x27;fa-plus&#x27; | fonticon&#x22; class=&#x22;speed-button btna fa&#x22;&#x3E;&#x3C;/Button&#x3E;
      &#x3C;Button row=&#x22;1&#x22; #btnd (tap)=&#x22;goToTeachersHome()&#x22; [@state]=&#x22; isOpen ? &#x27;activebtnb&#x27; : &#x27;inactivebtn&#x27; &#x22; [text]=&#x22;&#x27;fa-mortar-board&#x27; | fonticon&#x22; class=&#x22;speed-button btnb fa&#x22;&#x3E;&#x3C;/Button&#x3E;
      &#x3C;Button row=&#x22;1&#x22; #btne (tap)=&#x22;logout()&#x22; [@state]=&#x22; isOpen ? &#x27;activebtnc&#x27; : &#x27;inactivebtn&#x27; &#x22; [text]=&#x22;&#x27;fa-sign-out&#x27; | fonticon&#x22; class=&#x22;speed-button btne fa&#x22;&#x3E;&#x3C;/Button&#x3E;
     
      &#x3C;Fab row=&#x22;1&#x22; #fab [@state]=&#x22; isOpen ? &#x27;active&#x27; : &#x27;inactive&#x27; &#x22; (tap)=&#x22;onTap()&#x22; icon=&#x22;./images/menu.png&#x22; rippleColor=&#x22;#f1f1f1&#x22; class=&#x22;fab-button&#x22;&#x3E;&#x3C;/Fab&#x3E;
</code></pre>
   </p>
</div>
</li>
</li>
</ul>
