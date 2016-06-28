---
layout: post
title:  "Wire up a SegmentedBar"
date:   2016-03-30
categories: snippets
author: Nathan Walker
image: /videos/segmentedbar/thumb.png
tags: 
    - snippet
shortdesc: Nathan Walker shows us how to wire up a SegmentedBar. 
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
      <video controls autoplay loop="true" poster="/videos/segmentedbar/thumb.png">
        <source type="video/mp4" src="/videos/segmentedbar/1.mp4">
        <source type="video/webm" src="/videos/segmentedbar/2.webm">
        <source type="video/ogv" src="/videos/segmentedbar/3.ogv">
      </video>
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content1" class="tab-content">
      <pre class="language-html">
<code>&lt;SegmentedBar items="&lcub;&lcub;items&rcub;&rcub;" selectedIndexChanged="&lcub;&lcub;selectSegment&rcub;&rcub;" /&gt;
&lt;Label text="&lcub;&lcub;selectedItem&rcub;&rcub;" /&gt;
</code>
      </pre>
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">TypeScript</label>
    <div id="tab-content3" class="tab-content">
      <pre class="language-typescript">
        <code>

import {Observable} from &#x27;data/observable&#x27;;

export class Snippet extends Observable {
  public selectedItem: string;
  public items: Array&#x3C;any&#x3E; = [
    { title: &#x27;Strawberry&#x27; },
    { title: &#x27;Blueberry&#x27; },
    { title: &#x27;Raspberry&#x27; }
  ];

  constructor() {
    super();  
    this.selectedItem = &#x60;Selected: ${this.items[0].title}&#x60;; 
  }

  public selectSegment(e: any) {
    this.set(&#x27;selectedItem&#x27;, &#x60;Selected: ${this.items[e.newIndex].title}&#x60;);  
  }  
}

        </code>
      </pre>
    </div>
  </li>
</ul>
