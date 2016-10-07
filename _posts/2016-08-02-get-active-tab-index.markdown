---
layout: post
title:  "Get the Active Tab Index in a TabView"
date:   2016-08-02
categories: snippets
type: ng
image: /images/active-tab.gif
author: Steve P
tags: 
    - tabs
    - index
    - active
shortdesc: 	Get the index of the current selected tab for use outside the TabView. A partner snack by Steve P and Nathan Walker
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/active-tab.gif">
    </div>
  </li>


  
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">TypeScript</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-javascript">
        <code>
import {Component} from "@angular/core";

@Component({
 selector: "Tab-Snack",
 templateUrl: "./Pages/TabSnack/TabSnack.html"
})
export class TabSnack {
 public activeTab: string;

 public tabIndexChanged(e: any) {
   switch (e.newIndex) {
     case 0:
       console.log(`Selected tab index: ${e.newIndex}`);
       this.activeTab = "TabOne";
       break;
     case 1:
       console.log(`Selected tab index: ${e.newIndex}`);
       this.activeTab = "TabTwo";
       break;
     case 2:
       console.log(`Selected tab index: ${e.newIndex}`);
       this.activeTab = "TabThree";
       break;
     default:
       break;
   }
 }

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
&#x3C;ActionBar&#x3E;
 
 &#x3C;ActionItem&#x3E;
   &#x3C;ActionView&#x3E;
     &#x3C;Label text=&#x22;NG Active Tab Demo&#x22;&#x3E;&#x3C;/Label&#x3E;
   &#x3C;/ActionView&#x3E;
 &#x3C;/ActionItem&#x3E;
 
 
 &#x3C;ActionItem *ngIf=&#x22;activeTab == &#x27;TabOne&#x27;&#x22;&#x3E;
   &#x3C;Label row=&#x22;0&#x22; col=&#x22;2&#x22; text=&#x22;Tab One&#x22; width=&#x22;80&#x22;&#x3E;&#x3C;/Label&#x3E;
 &#x3C;/ActionItem&#x3E;
 &#x3C;ActionItem *ngIf=&#x22;activeTab == &#x27;TabTwo&#x27;&#x22;&#x3E;
   &#x3C;Label row=&#x22;0&#x22; col=&#x22;2&#x22; text=&#x22;Tab Two&#x22; width=&#x22;80&#x22;&#x3E;&#x3C;/Label&#x3E;
 &#x3C;/ActionItem&#x3E;
 &#x3C;ActionItem *ngIf=&#x22;activeTab == &#x27;TabThree&#x27;&#x22;&#x3E;
   &#x3C;Label row=&#x22;0&#x22; col=&#x22;2&#x22; text=&#x22;Tab Three&#x22; width=&#x22;80&#x22;&#x3E;&#x3C;/Label&#x3E;
 &#x3C;/ActionItem&#x3E;
 
&#x3C;/ActionBar&#x3E;

&#x3C;TabView #tabview (selectedIndexChanged)=&#x22;tabIndexChanged($event)&#x22;&#x3E;

 &#x3C;StackLayout *tabItem=&#x22;{title: &#x27;Tab1&#x27;}&#x22;&#x3E;
   &#x3C;Label text=&#x22;This is Label in Tab 1&#x22;&#x3E;&#x3C;/Label&#x3E;
 &#x3C;/StackLayout&#x3E;
 &#x3C;StackLayout *tabItem=&#x22;{title: &#x27;Tab2&#x27;}&#x22;&#x3E;
   &#x3C;Label text=&#x22;This is Label in Tab 2&#x22;&#x3E;&#x3C;/Label&#x3E;
 &#x3C;/StackLayout&#x3E;
 &#x3C;StackLayout *tabItem=&#x22;{title: &#x27;Tab3&#x27;}&#x22;&#x3E;
   &#x3C;Label text=&#x22;This is Label in Tab 3&#x22;&#x3E;&#x3C;/Label&#x3E;
 &#x3C;/StackLayout&#x3E;
 
&#x3C;/TabView&#x3E;
	
		</code>
  </pre>
</div>
</li>

 
</ul>
