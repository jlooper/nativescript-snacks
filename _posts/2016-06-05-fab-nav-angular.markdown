---
layout: post
title:  "Fab Button Navigation"
date:   2016-06-05
categories: snippets
type: ng
image: /images/fab-angular.gif
author: Jen Looper
tags: 
    - design
    - menu
    - UI
shortdesc: Jen builds on Brad's fab button plugin to create an expanding menu for Angular 2 apps
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/fab-angular.gif">
    </div>
  </li>
  
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">CSS</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-css">
        <code>
.speed-button {
    height: 50;
    width: 50;
    font-size: 20;
    text-align: center;
    color: #fff;
    opacity: 0;
    border-radius: 25;
    horizontal-align: center;
    vertical-align: bottom;
}
.btna {
  background-color: #493DF8; 
}
.btnb {
  background-color: #1598F6; 
}
.btnc {
  background-color: #6DE9C0; 
}
.btnd {
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
		</code>
      </pre>
    </div>
  </li>
<li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">XML</label>
    <div id="tab-content3" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;StackLayout&#x3E;
 
   &#x3C;GridLayout rows=&#x22;80,*,auto&#x22;&#x3E;
     
     &#x3C;CardView margin=&#x22;5&#x22; class=&#x22;cardStyle&#x22;&#x3E;
        &#x3C;Label text=&#x22;Welcome, Practice Buddy and Teachers!&#x22;&#x3E;&#x3C;/Label&#x3E;
     &#x3C;/CardView&#x3E;
      
      &#x3C;Button row=&#x22;1&#x22; #btna (tap)=&#x22;toggleNav(&#x27;Settings&#x27;)&#x22; [text]=&#x22;&#x27;fa-cog&#x27; | fonticon&#x22; class=&#x22;speed-button btna fa fa-cog&#x22;&#x3E;&#x3C;/Button&#x3E;
      &#x3C;Button row=&#x22;1&#x22; #btnb (tap)=&#x22;toggleNav(&#x27;Practice&#x27;)&#x22; [text]=&#x22;&#x27;fa-music&#x27; | fonticon&#x22; class=&#x22;speed-button btnb fa&#x22;&#x3E;&#x3C;/Button&#x3E;
      &#x3C;Button row=&#x22;1&#x22; #btnc (tap)=&#x22;toggleNav(&#x27;Calendar&#x27;)&#x22; [text]=&#x22;&#x27;fa-calendar&#x27; | fonticon&#x22; text=&#x22;three&#x22; class=&#x22;speed-button btnc fa&#x22;&#x3E;&#x3C;/Button&#x3E;
      &#x3C;Button row=&#x22;1&#x22; #btnd (tap)=&#x22;toggleNav(&#x27;Feedback&#x27;)&#x22; [text]=&#x22;&#x27;fa-comments&#x27; | fonticon&#x22; text=&#x22;four&#x22; class=&#x22;speed-button btnd fa&#x22;&#x3E;&#x3C;/Button&#x3E;
      &#x3C;Button row=&#x22;1&#x22; #btne (tap)=&#x22;toggleNav(&#x27;Teachers&#x27;)&#x22; [text]=&#x22;&#x27;fa-dashboard&#x27; | fonticon&#x22; text=&#x22;five&#x22; class=&#x22;speed-button btne fa&#x22;&#x3E;&#x3C;/Button&#x3E;
     
      &#x3C;Fab row=&#x22;1&#x22; #fab (tap)=&#x22;toggleNav(&#x27;Home&#x27;)&#x22; icon=&#x22;./images/icAddWhite.png&#x22; rippleColor=&#x22;#f1f1f1&#x22; class=&#x22;fab-button&#x22;&#x3E;&#x3C;/Fab&#x3E;
    
    &#x3C;/GridLayout&#x3E; 
 
 &#x3C;/StackLayout&#x3E;
      
		</code>
      </pre>
    </div>
  </li>
  
  <li>
    <input type="radio" name="tabs" id="tab4" />
    <label for="tab4">JavaScript</label>
    <div id="tab-content4" class="tab-content">
      <pre class="language-javascript">
        <code>
public _isFabOpen: boolean;
    
    @ViewChild("btna") btna: ElementRef;
    @ViewChild("btnb") btnb: ElementRef;
    @ViewChild("btnc") btnc: ElementRef;
    @ViewChild("btnd") btnd: ElementRef;
    @ViewChild("btne") btne: ElementRef;
    @ViewChild("fab") fab: ElementRef;
  
   toggleNav(id){
        
      if (this._isFabOpen === true) {
            let animations = [
                  { target: <View>this.fab.nativeElement, rotate: 0, duration: 280, delay: 0 },
                  { target: <View>this.btna.nativeElement, translate: { x: 0, y: 0 }, opacity: 0, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btnb.nativeElement, translate: { x: 0, y: 0 }, opacity: 0, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btnc.nativeElement, translate: { x: 0, y: 0 }, opacity: 0, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btnd.nativeElement, translate: { x: 0, y: 0 }, opacity: 0, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btne.nativeElement, translate: { x: 0, y: 0 }, opacity: 0, duration: 280, curve: AnimationCurve.easeOut, delay: 0 }
        ];

              var a = new Animation(animations);

              a.play()
                  .then(() => {
                      if(id !== "Home"){
                        this._router.navigate([id])
                      }
                      this._isFabOpen = false;
                  })
                  .catch(function (e) {
                      console.log(e.message);
                  });
        }
        else {
          let animations = [
                  { target: <View>this.fab.nativeElement, rotate: 45, duration: 280, delay: 0 },
                  { target: <View>this.btna.nativeElement, translate: { x: -90, y: -15 }, opacity: 1, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btnb.nativeElement, translate: { x: -75, y: -80 }, opacity: 1, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btnc.nativeElement, translate: { x: 0, y: -105 }, opacity: 1, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btnd.nativeElement, translate: { x: 75, y: -80 }, opacity: 1, duration: 280, curve: AnimationCurve.easeOut, delay: 0 },
                  { target: <View>this.btne.nativeElement, translate: { x: 90, y: -15 }, opacity: 1, duration: 280, curve: AnimationCurve.easeOut, delay: 0 }
              ];

              let a = new Animation(animations);

              a.play()
                  .then(() => {
                      this._isFabOpen = true;
                  })
                  .catch(function (e) {
                      console.log(e.message);
                  });
        }
    }      
		</code>
      </pre>
    </div>
  </li>
    
</ul>
