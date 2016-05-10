---
layout: post
title:  "NativeScript + Angular 2 Tab Navigation"
date:   2016-05-07
categories: snippets
image: /images/tab-nav.gif
author: Adam Rafeeq
tags: 
    - tabs
    - navigation
    - angular 2
shortdesc: Easy tab navigation using NativeScript and Angular 2. 
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/tab-nav.gif">
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
import {Component} from &#x22;angular2/core&#x22;;

@Component({
  selector: &#x22;my-app&#x22;,
  template: &#x60;
&#x3C;TabView #tabview&#x3E;
  &#x3C;StackLayout *tabItem=&#x22;{title: &#x27;Tab1&#x27;}&#x22;&#x3E;
    &#x3C;Label text=&#x22;This is Label in Tab 1&#x22;&#x3E;&#x3C;/Label&#x3E;
  &#x3C;/StackLayout&#x3E;
  &#x3C;StackLayout *tabItem=&#x22;{title: &#x27;Tab2&#x27;}&#x22;&#x3E;
    &#x3C;Label text=&#x22;This is Label in Tab 2&#x22;&#x3E;&#x3C;/Label&#x3E;
  &#x3C;/StackLayout&#x3E;
&#x3C;/TabView&#x3E;
&#x60;
})
export class myApp {
}
        </code>
      </pre>
    </div>
  </li>
</ul>
