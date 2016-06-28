---
layout: post
title:  "Assigning Child Component Elements To Parent GridLayout"
date:   2016-06-20
categories: snippets
type: ng
image: /images/gridlayout.png
author: Don Burgess
tags: 
    - gridlayout
    - child
    - component
shortdesc: 	Child components can't be assigned to gridlayouts, but the child component's elements can be
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/gridlayout.png">
    </div>
  </li>
    
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">TypeScript</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-javascript">
        <code>

import {
    Component,
    OnInit,
    Input,
    AfterViewInit,
    ElementRef,
    ViewChild
}                               from "@angular/core";
​
// UI
import {StackLayout}            from "ui/layouts/stack-layout";
import {GridLayout}             from "ui/layouts/grid-layout";
​
@Component({
    selector: "child-component",
    directives: [],
    providers: [],
    template: `
        &#x3C;StackLayout #container
            orientation=&#x22;horizontal&#x22;
            verticalAlignment=&#x22;center&#x22;&#x3E;
&#x200B;
            &#x3C;Label
                text=&#x22;Hello&#x22;&#x3E;
            &#x3C;/Label&#x3E;
&#x200B;
            &#x3C;Switch
                checked=&#x22;false&#x22;&#x3E;
            &#x3C;/Switch&#x3E;
        &#x3C;/StackLayout&#x3E;
    `
})
export class ChildComponent implements OnInit, AfterViewInit {
​
    // Elements
    @ViewChild("container") container: ElementRef;
    
    constructor(){}
​
    ngAfterViewInit(){
        // Assign the element in template to a variable
      	const container = <StackLayout>this.container.nativeElement;
​		
		// GridLayout has static functions setRow and setColumn.
		// Pass in your element to these static functions and they will attach to the closest parent gridlayout
        GridLayout.setRow(container, 0);
        GridLayout.setColumn(container, 1);
        }
    }
}

		
        </code>
      </pre>
    </div>
  </li>
    
</ul>
