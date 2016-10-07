---
layout: post
title:  "A Cool Image Carousel"
date:   2016-05-22
categories: snippets
image: /images/image-carousel.gif
author: Brad Martin
tags: 
    - design
    - image carousel
    - slides
shortdesc: Brad shows how to create an image carousel with his NativeScript-Slides plugin.
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/image-carousel.gif">
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;Page xmlns=&#x22;http://schemas.nativescript.org/tns.xsd&#x22; xmlns:Slides=&#x22;nativescript-slides&#x22; loaded=&#x22;pageLoaded&#x22;&#x3E;

&#x9;&#x3C;StackLayout&#x3E;
&#x9;&#x9;&#x3C;GridLayout height=&#x22;300&#x22; rows=&#x22;*, auto, *&#x22; columns=&#x22;auto, *, auto&#x22;&#x3E;
&#x9;&#x9;
&#x9;&#x9;&#x9;&#x3C;Button row=&#x22;1&#x22; col=&#x22;0&#x22; text=&#x22;&#x26;#xf053;&#x22; tap=&#x22;prev&#x22; class=&#x22;carousel-btn FontAwesome&#x22; /&#x3E;
&#x9;&#x9;&#x9;
&#x9;&#x9;&#x9;&#x3C;Slides:SlideContainer height=&#x22;100%&#x22; row=&#x22;1&#x22; colSpan=&#x22;3&#x22; loop=&#x22;true&#x22; id=&#x22;slideContainer&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Slides:Slide class=&#x22;image-slide&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x9;&#x3C;Image src=&#x22;~/images/wolverine.jpeg&#x22; stretch=&#x22;aspectFill&#x22; class=&#x22;slideImage&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;/Slides:Slide&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Slides:Slide class=&#x22;image-slide&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x9;&#x3C;Image src=&#x22;~/images/spiderman.jpeg&#x22; stretch=&#x22;aspectFill&#x22; class=&#x22;slideImage&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;/Slides:Slide&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Slides:Slide class=&#x22;image-slide&#x22;&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x9;&#x3C;Label text=&#x22;Let&#x27;s make app slides great again.&#x22; textWrap=&#x22;true&#x22; class=&#x22;title&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;/Slides:Slide&#x3E;
&#x9;&#x9;&#x9;&#x3C;/Slides:SlideContainer&#x3E;
&#x9;&#x9;&#x9;
&#x9;&#x9;&#x9;&#x3C;Button row=&#x22;1&#x22; col=&#x22;2&#x22; text=&#x22;&#x26;#xf054;&#x22; tap=&#x22;next&#x22; class=&#x22;carousel-btn FontAwesome&#x22; /&#x3E;
&#x9;&#x9;&#x9;
&#x9;&#x9;&#x3C;/GridLayout&#x3E;
&#x9;&#x9;
&#x9;&#x9;&#x3C;ScrollView&#x3E;
&#x9;&#x9;
&#x9;&#x9;&#x9;&#x3C;StackLayout&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Label text=&#x22;Bacon ipsum dolor amet short loin corned beef pork loin ham hock jowl chicken. Strip steak venison cupim capicola brisket tail ball tip flank meatloaf doner pork chop. Shank venison shankle leberkas landjaeger. Ground round beef ribs cow, porchetta pork doner ham hock venison tenderloin landjaeger shankle pancetta leberkas biltong. Flank rump short ribs kevin frankfurter cupim venison strip steak picanha ground round filet mignon short loin sausage corned beef.&#x22; textWrap=&#x22;true&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Label text=&#x22;Bacon ipsum dolor amet short loin corned beef pork loin ham hock jowl chicken. Strip steak venison cupim capicola brisket tail ball tip flank meatloaf doner pork chop. Shank venison shankle leberkas landjaeger. Ground round beef ribs cow, porchetta pork doner ham hock venison tenderloin landjaeger shankle pancetta leberkas biltong. &#x22; textWrap=&#x22;true&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x9;&#x3C;Label text=&#x22;Bacon ipsum dolor amet short loin corned beef pork loin ham hock jowl chicken. Strip steak venison cupim capicola brisket tail ball tip flank meatloaf doner pork chop. Shank venison shankle leberkas landjaeger. Ground round beef ribs cow, porchetta pork doner ham hock venison tenderloin landjaeger shankle pancetta leberkas biltong. &#x22; textWrap=&#x22;true&#x22; /&#x3E;
&#x9;&#x9;&#x9;&#x3C;/StackLayout&#x3E;
&#x9;&#x9;&#x9;
&#x9;&#x9;&#x3C;/ScrollView&#x3E;
&#x9;&#x3C;/StackLayout&#x3E;
&#x9;
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
.carousel-btn {
  color: #fff;
  font-size: 25;
  background-color: rgba(#3489db, green, blue, 0.4);
  border-radius: 40;
  height: 60;
  vertical-align: bottom;
}

.FontAwesome {
    font-family: FontAwesome;
}

.title {
  color: #f1f1f1;
  font-size: 35;
}

.image-slide {
  background-color: #222;
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
        
var page;
var slideContainer;


// Event handler for Page "loaded" event attached in main-page.xml
function pageLoaded(args) {
    // Get the event sender
    page = args.object;
    page.actionBarHidden = true;
    slideContainer = page.getViewById('slideContainer');
    console.log(slideContainer);
}
exports.pageLoaded = pageLoaded;


function next(args) {
    console.log('Next slide');
    slideContainer.nextSlide();
}
exports.next = next;


function prev(args) {
    console.log('Previous slide');
    slideContainer.previousSlide();
}
exports.prev = prev;
		</code>
      </pre>
    </div>
  </li>
  
</ul>
