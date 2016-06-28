---
layout: post
title:  "RxJS Observable binding to ListView in {N} + Angular"
date:   2016-06-07
categories: snippets
type: ng
image: /images/observables.png
author: Nathan Walker
tags: 
    - angular
    - observable
    - behaviorsubject
    - onpush
    - change detection
shortdesc: BehaviorSubject is a type of Observable that works really well to bind your data using Angular's `async` pipe. Doing so allows you to take advantage of Angular's performance enhanced change detection strategy, `OnPush`.
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/observables-large.png">
    </div>
  </li>
  
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">TypeScript</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-javascript">
        <code>
import {Component, ChangeDetectionStrategy} from '@angular/core';
import {BehaviorSubject} from "rxjs/BehaviorSubject";

@Component({
  selector:'sample-cmp',
  template:`
  &#x3C;StackLayout&#x3E;
    &#x3C;Button (tap)=&#x22;addItem()&#x22; text=&#x22;Add Item&#x22;&#x3E;&#x3C;/Button&#x3E;
    &#x3C;ListView [items]=&#x22;items$ | async&#x22; (itemTap)=&#x22;itemTap($event)&#x22;&#x3E;
      &#x3C;template let-item=&#x22;item&#x22; let-odd=&#x22;odd&#x22; let-even=&#x22;even&#x22;&#x3E;
        &#x3C;StackLayout [class.odd]=&#x22;odd&#x22; [class.even]=&#x22;even&#x22;&#x3E;
          &#x3C;Label [text]=&#x22;item&#x22; textWrap=&#x22;true&#x22;&#x3E;&#x3C;/Label&#x3E;  
        &#x3C;/StackLayout&#x3E;
      &#x3C;/template&#x3E;
    &#x3C;/ListView&#x3E;
  &#x3C;/StackLayout&#x3E;
  `,
  changeDetection: ChangeDetectionStrategy.OnPush
})
export class SampleComponent {
  public items$: BehaviorSubject<Array<string>> = new BehaviorSubject([]);
  private _items: Array<string>;
  
  constructor() {
    this._items = [
      'Item 1',
      'Item 2',
      'Item 3'
    ];
    this.items$.next(this._items);
  }

  public addItem() {
    this._items.push(`Item ${this._items.length+1}`);
    // important to always push a new Array
    // to properly update the view (immutability)
    this.items$.next([...this._items]);
    
    // this would be the wrong way
    // this.items$.next(this._items);
  }
}
		</code>
      </pre>
    </div>
  </li>
    
</ul>
