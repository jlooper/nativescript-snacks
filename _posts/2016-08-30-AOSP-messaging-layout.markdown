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
import {Component, OnInit} from &#x22;@angular/core&#x22;
import {NS_ROUTER_DIRECTIVES} from &#x22;nativescript-angular/router&#x22;
import {SMSService} from &#x22;~/services/sms.service&#x22;



@Component({
&#x9;directives: [NS_ROUTER_DIRECTIVES],
&#x9;styleUrls: [&#x22;pages/sandbox/sandbox.styles.css&#x22;],
&#x9;templateUrl: &#x22;pages/sandbox/sandbox.template.html&#x22;,
&#x9;providers: [SMSService], // this service gets device conversations and contacts
})

export class AddLiveComponent implements OnInit {

&#x9;conversations: Array&#x3C;any&#x3E; = []

&#x9;constructor(
&#x9;&#x9;private smsService: SMSService
&#x9;) {}

&#x9;ngOnInit() {
&#x9;&#x9;this.getConversations()
&#x9;}

&#x9;getConversations() {
&#x9;&#x9;this.smsService.getConversations().then((conversations) =&#x3E; {
&#x9;&#x9;&#x9;this.conversations = conversations
&#x9;&#x9;}).catch(function(error) {
&#x9;&#x9;&#x9;global.tnsconsole.error(&#x27;error&#x27;, error)
&#x9;&#x9;})

&#x9;}

}
   </code>
  </pre>
</div>
</li>
</ul>
