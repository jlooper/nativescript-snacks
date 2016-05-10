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
<code>import {Observable} from 'data/observable';

export class Snippet extends Observable {
  public selectedItem: string;
  public items: Array<any> = [
    { title: 'Strawberry' },
    { title: 'Blueberry' },
    { title: 'Raspberry' }
  ];

  constructor() {
    super();  
    this.selectedItem = `Selected: ${this.items[0].title}`; 
  }

  public selectSegment(e: any) {
    this.set('selectedItem', `Selected: ${this.items[e.newIndex].title}`);  
  }  
}</code>
      </pre>
    </div>
  </li>
</ul>
