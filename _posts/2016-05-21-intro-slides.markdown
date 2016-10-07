---
layout: post
title:  "Create Intro Slides"
date:   2016-05-21
categories: snippets
image: /images/intro-slides.gif
author: Brad Martin
tags: 
    - app intro
    - animations
    - slides
    - swipe panels
shortdesc: Brad shows how easy it is to create an app intro with swipeable slides.
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/intro-slides.gif">
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;Page xmlns=&#x22;http://schemas.nativescript.org/tns.xsd&#x22; xmlns:Slides=&#x22;nativescript-slides&#x22; loaded=&#x22;pageLoaded&#x22;&#x3E;
&#x9;&#x3C;GridLayout rows=&#x22;*, auto&#x22; cols=&#x22;*, auto, *&#x22;&#x3E;
&#x9;&#x9;&#x3C;Slides:SlideContainer id=&#x22;slideContainer&#x22; class=&#x22;coverImage&#x22; row=&#x22;0&#x22; colSpan=&#x22;3&#x22; androidTranslucentStatusBar=&#x22;true&#x22; androidTranslucentNavBar=&#x22;false&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x3C;Slides:Slide class=&#x22;transparent&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Label margin=&#x22;250&#x22; row=&#x22;0&#x22; colSpan=&#x22;3&#x22; text=&#x22;Welcome Coders!&#x22; textWrap=&#x22;true&#x22; class=&#x22;title&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x3C;/Slides:Slide&#x3E;
&#x9;&#x9;&#x9;&#x3C;Slides:Slide class=&#x22;transparent&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;GridLayout rows=&#x22;*, auto&#x22; cols=&#x22;*, auto, *&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x9;&#x3C;Image row=&#x22;0&#x22; colSpan=&#x22;3&#x22; src=&#x22;~/images/rocketTwo.png&#x22; stretch=&#x22;aspectFit&#x22; class=&#x22;slideImage&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x9;&#x3C;Label row=&#x22;1&#x22; colSpan=&#x22;3&#x22; text=&#x22;Interact and engage your audience. Trust us, this will pull them in.&#x22; textWrap=&#x22;true&#x22; class=&#x22;message&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;/GridLayout&#x3E;
&#x9;&#x9;&#x9;&#x3C;/Slides:Slide&#x3E;
&#x9;&#x9;&#x9;&#x3C;Slides:Slide class=&#x22;transparent&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Label row=&#x22;0&#x22; colSpan=&#x22;3&#x22; text=&#x22;Let&#x27;s make app slides great again.&#x22; textWrap=&#x22;true&#x22; class=&#x22;title&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x3C;/Slides:Slide&#x3E;
&#x9;&#x9;&#x3C;/Slides:SlideContainer&#x3E;
&#x9;&#x9;&#x3C;GridLayout class=&#x22;slideFooter&#x22; row=&#x22;1&#x22; colSpan=&#x22;3&#x22; rows=&#x22;*&#x22; columns=&#x22;*, *&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x3C;Button class=&#x22;footerBtn&#x22; text=&#x22;Prev&#x22; tap=&#x22;prev&#x22; row=&#x22;0&#x22; col=&#x22;0&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x3C;Button class=&#x22;footerBtn&#x22; text=&#x22;Next&#x22; tap=&#x22;next&#x22; row=&#x22;0&#x22; col=&#x22;1&#x22; /&#x3E;
&#x9;&#x9;&#x3C;/GridLayout&#x3E;
&#x9;&#x3C;/GridLayout&#x3E;
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
.coverImage {
    background-image: ~/images/ufo.png;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}

.transparent {
  background-color: transparent;
}

.title {
  color: #f1f1f1;
  font-size: 35;
}

.message {
  font-size: 20;
  margin: 8;
  color: #f1f1f1;
}

.slideFooter {
  background-color: transparent;
}

.footerBtn {
  background-color: white;
  color: #333;
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
        <code>
        
import { EventData } from 'data/observable';
import * as pages from 'ui/page';

let page: pages.Page;
let slideContainer: any;

// Event handler for Page "loaded" event attached in main-page.xml
export function pageLoaded(args: EventData) {
	// Get the event sender
	page = <pages.Page>args.object;
	page.actionBarHidden = true;
	slideContainer = page.getViewById('slideContainer');
	console.log(slideContainer);	
}

export function next(args: EventData) {
	console.log('Next slide');
	slideContainer.nextSlide();
} 
 
export function prev(args: EventData) {
	console.log('Previous slide');
	slideContainer.previousSlide();
}

		</code>
      </pre>
    </div>
  </li>
  
</ul>
