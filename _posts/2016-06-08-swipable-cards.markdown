---
layout: post
title:  "Tinder-Style Swipable Cards"
date:   2016-06-07
categories: snippets
image: /images/swipable-cards.gif
author: Jen Looper
tags: 
    - cards
    - swipable
    - Tinder
shortdesc: Swipe left, swipe right, find your true match!
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/swipable-cards.gif">
    </div>
  </li>
  
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">CSS</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-css">
        <code>
Page {
	background-color: white;
}
Image {
	margin: 10;
}
.card{
	margin:20px;
	background-color:#03A9F4;
	border-radius:5;
}
Label{
	font:40;
	color:white;
}		</code>
      </pre>
    </div>
  </li>
<li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">XML</label>
    <div id="tab-content3" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;Page loaded=&#x22;loaded&#x22;&#x3E;&#x9;
  &#x3C;Page.actionBar&#x3E;&#x9;&#x9;
    &#x3C;ActionBar title=&#x22;Hello!&#x22; id=&#x22;verdict&#x22;&#x3E;&#x3C;/ActionBar&#x3E;
  &#x3C;/Page.actionBar&#x3E;&#x9;&#x9;
    &#x3C;StackLayout id=&#x22;card&#x22; class=&#x22;card&#x22;&#x3E;
    &#x9;&#x3C;Image id=&#x22;guy&#x22;&#x3E;&#x3C;/Image&#x3E;
    &#x9;&#x3C;Label id=&#x22;name&#x22;&#x3E;&#x3C;/Label&#x3E;
    &#x9;&#x3C;Label id=&#x22;job&#x22;&#x3E;&#x3C;/Label&#x3E;
    &#x9;&#x3C;Label id=&#x22;age&#x22;&#x3E;&#x3C;/Label&#x3E;
    &#x3C;/StackLayout&#x3E;
&#x3C;/Page&#x3E;      
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
var actionBarUtil = require("../../shared/utils/action-bar-util");
var gestures = require("ui/gestures");
var _page;

exports.loaded = function(args) {

	_page = args.object;
	_page.bindingContext = user;
	actionBarUtil.styleActionBar();
    actionBarUtil.hideiOSBackButton();

    var card = _page.getViewById("card");
    var img = _page.getViewById("guy");
    var job = _page.getViewById("job");
    var age = _page.getViewById("age");
    var name = _page.getViewById("name");

    var namesArray = ["Floyd","Pete","Brian","Randall","Jim","Ashef","Michel","Drake","Ed"];
    var jobsArray = ["Developer","Food Editor","Journalist","Actor","Fisherman","Chef","Designer","Musician","Baker"];
    var ageArray = [41,23,35,33,45,64,33,54,34];
    
    var i = 0;
	
	//set a default
	img.src="~/images/"+i+".jpg"; 
	job.text=jobsArray[i];
	age.text=ageArray[i];
	name.text=namesArray[i];
   
    var verdict = _page.getViewById("verdict");
    card.on(gestures.GestureTypes.swipe, function (args) {

    	i = i + 1;
    			
    	if(args.direction === 1){
			verdict.title="Yea!";
    		card.animate({ translate: { x: 1000, y: 100 } })
    			.then(function () { return card.animate({ translate: { x: 0, y: -2000 } }); })			    
			    .then(function () { return card.animate({ translate: { x: 0, y: 0 } }); })			    
			    .then(function () {
					img.src="~/images/"+i+".jpg"; 
					job.text=jobsArray[i];
					age.text=ageArray[i];
					name.text=namesArray[i];   	
			})
			    .catch(function (e) {
			    console.log(e.message);
			});
		}
		else{
			verdict.title="Nay!";
			card.animate({ translate: { x: -1000, y: 100 } })
				.then(function () { return card.animate({ translate: { x: 0, y: -2000 } }); })			    
			    .then(function () { return card.animate({ translate: { x: 0, y: 0 } }); })			    
			    .then(function () {			    
					img.src="~/images/"+i+".jpg"; 
					job.text=jobsArray[i];
					age.text=ageArray[i]; 
					name.text=namesArray[i];   
    	
			})
			    .catch(function (e) {
			    console.log(e.message);
			});
		}
      
	});

	
};

		</code>
      </pre>
    </div>
  </li>
    
</ul>
