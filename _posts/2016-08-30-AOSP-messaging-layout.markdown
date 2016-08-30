---
layout: post
title:  "AOSP Messaging Layout Example"
date:   2016-08-30
categories: snippets
type: ng
image: /images/aosp.png
author: Robert Laverty
tags: 
    - css
    - layouts
    - angular
shortdesc: 	Layout example on how to mimic the AOSP Messages conversation layout on Android
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/aosp.png">
    </div>
</li>
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
&#x3C;ListView id=&#x22;threadsListView&#x22; class=&#x22;threads-list&#x22; [items]=&#x22;conversations&#x22;&#x3E;
    &#x3C;template let-item=&#x22;item&#x22;&#x3E;
        &#x3C;GridLayout rows=&#x22;auto&#x22; columns=&#x22;auto,*&#x22; class=&#x22;threads-list-wrapper&#x22;&#x3E;
            &#x3C;Image row=&#x22;0&#x22; col=&#x22;0&#x22; [src]=&#x22;item.photo&#x22;&#x3E;&#x3C;/Image&#x3E;
            &#x3C;StackLayout row=&#x22;0&#x22; col=&#x22;1&#x22; class=&#x22;&#x22; orientation=&#x22;vertical&#x22;&#x3E;
                &#x3C;Label class=&#x22;t-large&#x22; [text]=&#x22;item.title&#x22;&#x3E;&#x3C;/Label&#x3E;
                &#x3C;Label [text]=&#x22;item.body&#x22;&#x3E;&#x3C;/Label&#x3E;
                &#x3C;Label [text]=&#x22;item.date&#x22;&#x3E;&#x3C;/Label&#x3E;
            &#x3C;/StackLayout&#x3E;
        &#x3C;/GridLayout&#x3E;
    &#x3C;/template&#x3E;
&#x3C;/ListView&#x3E;
		</code>
  </pre>
</div>
</li>     
<li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">CSS</label>
    <div id="tab-content3" class="tab-content">
      <pre class="language-javascript">
  <code>
.threads-list-wrapper {
    padding: 15;
}

.threads-list-wrapper > Image {
    height: 64;
    width: 64;
    margin-right: 15;
}
   </code>
  </pre>
</div>
</li>
<li>
    <input type="radio" name="tabs" id="tab4" />
    <label for="tab4">TypeScript</label>
    <div id="tab-content4" class="tab-content">
      <pre class="language-javascript">
  <code>
import {Component, OnInit} from "@angular/core"
import {NS_ROUTER_DIRECTIVES} from "nativescript-angular/router"
import {SMSService} from "~/services/sms.service"



@Component({
	directives: [NS_ROUTER_DIRECTIVES],
	styleUrls: ["pages/sandbox/sandbox.styles.css"],
	templateUrl: "pages/sandbox/sandbox.template.html",
	providers: [SMSService], // this service gets device conversations and contacts
})

export class AddLiveComponent implements OnInit {

	conversations: Array<any> = []

	constructor(
		private smsService: SMSService
	) {}

	ngOnInit() {
		this.getConversations()
	}

	getConversations() {
		this.smsService.getConversations().then((conversations) => {
			this.conversations = conversations
		}).catch(function(error) {
			global.tnsconsole.error('error', error)
		})

	}

}
   </code>
  </pre>
</div>
</li>
</ul>
