---
layout: post
title:  "A SegmentedBar with NativeScript and Angular 2"
date:   2016-06-22
categories: snippets
type: ng
image: /images/angular-sb.gif
author: Osei Fortune
tags: 
    - segmentedbar
    - navigation
shortdesc: 	Osei creates a simple segmentedbar in {N} + ng2 programmatically
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/angular-sb.gif">
    </div>
  </li>
    
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">TypeScript</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-javascript">
        <code>
import {Component, OnInit, OnDestroy, AfterViewInit, ViewChild, ElementRef} from '@angular/core';
import {Page} from 'ui/page';
import {SegmentedBar, SegmentedBarItem, SelectedIndexChangedEventData} from 'ui/segmented-bar';
@Component({
    selector: 'tabs',
    template: '&#x3C;SegmentedBar #tabs [items]=&#x22;items&#x22; [selectedIndex]=&#x22;selectedIndex&#x22;&#x3E;&#x3C;/SegmentedBar&#x3E;'
})
export class TabsComponent implements OnInit, OnDestroy, AfterViewInit {
    selectedIndex: number;
    items: Array<any>;
    @ViewChild("tabs") tabs: ElementRef;
    constructor(private router: Router, private page: Page) {
        this.selectedIndex = 0;
        this.items = [{ title: 'First' }, { title: 'Second' }, { title: 'Third' }];
}
    ngOnInit() {

    }
    ngAfterViewInit() {
        this.tabs.nativeElement.on(SegmentedBar.selectedIndexChangedEvent, (args: SelectedIndexChangedEventData) => {
            switch (args.newIndex) {
                case 0:
                    console.log('first selected')
                    break;
                case 1:
                    console.log('second selected')
                    break;
                case 3:
                    console.log('third selected')
                    break;
            }
        })
    }
    ngOnDestroy() { }
}

		</code>
      </pre>
    </div>
  </li>
    
</ul>
