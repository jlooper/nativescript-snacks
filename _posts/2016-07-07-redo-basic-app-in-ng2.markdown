---
layout: post
title:  "Accessing NativeScript controls in Angular 2 with ViewChild"
date:   2016-07-07
categories: snippets
type: ng
image: /images/redo.gif
author: Josh Sommer
tags: 
    - ViewChild
    - Angular
    - ElementRef
shortdesc: 	Josh redoes the basic 'hello world' app in Angular, demonstrating how to access and set control properties using ViewChild
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/redo.gif">
    </div>
  </li>


  
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">TypeScript</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-javascript">
        <code>
import {Component, ViewChild, ElementRef, AfterViewInit} from "@angular/core";
import {Button} from "ui/button";

@Component({
    selector: "my-app",
    templateUrl: "app.component.html",
})
export class AppComponent implements AfterViewInit {
    @ViewChild("button") button: ElementRef;

    public counter: number = 16;

    public onTap() {
        let viewButton: Button = this.button.nativeElement;
        this.counter--;
        // sets the button text on each tap.
        viewButton.text = `${this.counter} taps left`;
        if (this.counter === 0) {
            viewButton.text = "Hoorraaay!";
        }
    }

    ngAfterViewInit(): void {
        // sets the button text after load
        let viewButton: Button = this.button.nativeElement;
        viewButton.text = `TAPS Left ${this.counter}`;
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
&#x3C;StackLayout&#x3E;
    &#x3C;Label text=&#x22;Tap the button&#x22; class=&#x22;title&#x22;&#x3E;&#x3C;/Label&#x3E;
    &#x3C;Button #button text=&#x22;TAP&#x22; (tap)=&#x22;onTap()&#x22;&#x3E;&#x3C;/Button&#x3E;
&#x3C;/StackLayout&#x3E;
	
		    </code>
  </pre>
</div>
</li>

 
</ul>
