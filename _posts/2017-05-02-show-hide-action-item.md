---
layout: post
title:  "Hiding or Showing an ActionItem in Angular"
date:   2017-05-02
categories: snippets
image: /images/actionitem.jpg
type: ng
author: Rachid Al Khayat
tags: 
    - action item
    - angular
shortdesc: 	In this snippet, Rachid shows that hiding or showing an ActionItem is easy in Angular
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/actionitem.jpg">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">JavaScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-javascript">
        <code>
import {Component, OnInit} from '@angular/core';
@Component({
  moduleId: module.id,
  selector: "gf-list-detail",
  templateUrl: "list-detail.html"
})
export class ListDetailComponent implements OnInit {
	public isEditing:boolean;
  
  constructor() {
    
  }
  
  ngOnInit() {
  	this.isEditing = false;
  }
  
	onEdit(){
  		this.isEditing = true;
	}
  
	onCancel(){
  		this.isEditing = false;
	}
  
}
        </code>
    </pre>
   </p>
</div>
</li>

<li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">XML</label>
    <div id="tab-content3" class="tab-content">
      <p>
      <pre class="language-javascript">
        <code>
&#x3C;ActionBar class=&#x22;action-bar&#x22; title=&#x22;&#x22;&#x3E;
    &#x3C;NavigationButton text=&#x22;back&#x22; android.systemIcon=&#x22;ic_menu_back&#x22; (tap)=&#x22;back()&#x22;&#x3E;&#x3C;/NavigationButton&#x3E;
      &#x3C;ActionItem (tap)=&#x22;onEdit()&#x22; ios.systemIcon=&#x22;2&#x22; android.systemIcon=&#x22;ic_menu_edit&#x22; ios.position=&#x22;right&#x22;
                    visibility=&#x22;{{ isEditing ? &#x27;collapse&#x27; : &#x27;visible&#x27; }}&#x22;&#x3E;
      &#x3C;/ActionItem&#x3E;
      &#x3C;ActionItem (tap)=&#x22;onCancel()&#x22;  ios.systemIcon=&#x22;1&#x22; android.systemIcon=&#x22;ic_menu_close_clear_cancel&#x22;
                    visibility=&#x22;{{ isEditing ? &#x27;visible&#x27; : &#x27;collapse&#x27; }}&#x22;&#x3E;
      &#x3C;/ActionItem&#x3E;
      &#x3C;ActionItem (tap)=&#x22;editArticle(id)&#x22;
            ios.systemIcon=&#x22;3&#x22; ios.position=&#x22;left&#x22;
            android.systemIcon=&#x22;ic_menu_save&#x22; android.position=&#x22;actionBar&#x22;
            visibility=&#x22;{{ isEditing ? &#x27;visible&#x27; : &#x27;collapse&#x27; }}&#x22;&#x3E;
      &#x3C;/ActionItem&#x3E;
      &#x3C;ActionItem (tap)=&#x22;onSelectSingleTap()&#x22;
            ios.systemIcon=&#x22;15&#x22; ios.position=&#x22;left&#x22;
            android.systemIcon=&#x22;ic_menu_gallery&#x22; android.position=&#x22;actionBar&#x22;
            visibility=&#x22;{{ isEditing ? &#x27;visible&#x27; : &#x27;collapse&#x27; }}&#x22;&#x3E;
      &#x3C;/ActionItem&#x3E;
      &#x3C;ActionItem (tap)=&#x22;takePhoto()&#x22;
            ios.systemIcon=&#x22;15&#x22; ios.position=&#x22;left&#x22;
            android.systemIcon=&#x22;ic_menu_camera&#x22; android.position=&#x22;actionBar&#x22;
            visibility=&#x22;{{ isEditing ? &#x27;visible&#x27; : &#x27;collapse&#x27; }}&#x22;&#x3E;
      &#x3C;/ActionItem&#x3E;
    &#x3C;ActionItem (tap)=&#x22;goHome()&#x22;
            ios.systemIcon=&#x22;9&#x22; ios.position=&#x22;left&#x22;
            android.systemIcon=&#x22;ic_menu_home&#x22; android.position=&#x22;actionBar&#x22;&#x3E;
      &#x3C;/ActionItem&#x3E;
    &#x3C;ActionItem (tap)=&#x22;logout()&#x22; android.position=&#x22;popup&#x22; ios.position=&#x22;left&#x22; text=&#x22;&#x62E;&#x631;&#x648;&#x62C;&#x22;&#x3E;
      &#x3C;/ActionItem&#x3E;
&#x3C;/ActionBar&#x3E;
        </code>
    </pre>
   </p>
</div>
</li>


</ul>
