---
layout: post
title:  "Repeated Cards in an Angular 2 Layout"
date:   2016-06-28
categories: snippets
type: ng
image: /images/repeated-cards.png
author: Jen Looper
tags: 
    - cards
    - repeater
    - ngFor
shortdesc: 	You can't use a Repeater in an ng2+{N} app, but you can use *ngFor and have some fun with repeated cards!
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/repeated-cards.png">
    </div>
  </li>


  <li>
  <input type="radio" name="tabs" id="tab2" />
      <label for="tab2">XML</label>
        <div id="tab-content2" class="tab-content">
          <pre class="language-html">
           <code>
        
&#x3C;ActionBar title=&#x22;Home&#x22;&#x3E;
&#x3C;/ActionBar&#x3E;

&#x3C;StackLayout&#x3E;
 &#x3C;GridLayout rows=&#x22;*,auto,auto&#x22;&#x3E;
    &#x3C;ScrollView&#x3E;
      &#x3C;StackLayout&#x3E;        
        &#x3C;CardView class=&#x22;innerCardStyle&#x22;&#x3E;
            &#x3C;StackLayout&#x3E;          
              &#x3C;Label class=&#x22;header&#x22; text=&#x22;Welcome!&#x22;&#x3E;&#x3C;/Label&#x3E;          
              &#x3C;Label textWrap=&#x22;true&#x22; text=&#x22;Practice Buddy helps students become better musicians, and music teachers mentor their students.&#x22;&#x3E;&#x3C;/Label&#x3E;
            &#x3C;/StackLayout&#x3E;
        &#x3C;/CardView&#x3E;
        
      &#x3C;WrapLayout horizontalAlignment=&#x22;center&#x22;&#x3E;
          &#x3C;CardView radius=&#x22;5&#x22; class=&#x22;innerCardStyle&#x22; width=&#x22;40%&#x22; *ngFor=&#x22;let student of studentList&#x22;&#x3E;
            &#x3C;StackLayout horizontalAlignment=&#x22;center&#x22;&#x3E;
              &#x3C;Label horizontalAlignment=&#x22;center&#x22; class=&#x22;header&#x22; [text]=&#x22;student.Name&#x22;&#x3E;&#x3C;/Label&#x3E;
              &#x3C;Label horizontalAlignment=&#x22;center&#x22; text=&#x22;Working towards:&#x22;&#x3E;&#x3C;/Label&#x3E;
              &#x3C;Image #instrument&#x3E;&#x3C;/Image&#x3E;
              &#x3C;Label horizontalAlignment=&#x22;center&#x22; textWrap=&#x22;true&#x22; [text]=&#x22;student.Reward&#x22;&#x3E;&#x3C;/Label&#x3E;
            &#x3C;/StackLayout&#x3E;
          &#x3C;/CardView&#x3E;
        &#x3C;/WrapLayout&#x3E;
      &#x3C;/StackLayout&#x3E;
    &#x3C;/ScrollView&#x3E;
   &#x3C;/GridLayout&#x3E; 
 &#x3C;/StackLayout&#x3E;

        
        </code>
      </pre>
    </div>
  
  </li> 

    
  <li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">TypeScript</label>
    <div id="tab-content3" class="tab-content">
      <pre class="language-javascript">
        <code>

import { Component, ElementRef, ViewChild, OnInit} from "@angular/core";
import { View} from 'ui/core/view';
import {Router} from "@angular/router-deprecated";
import {Student} from "../../shared/student/student";
import {StudentListService} from "../../shared/student/student-list.service";

@Component({
  selector: 'home',
  templateUrl: 'components/home/home.html',
  styleUrls: ['components/home/home-common.css'],
  pipes: [TNSFontIconPipe],
  providers: [StudentListService]
})

export class HomeComponent implements OnInit {
    studentList: Array<Student> = [];
    isLoading = false;
    
    constructor(private _studentListService: StudentListService, private fonticon: TNSFontIconService, private _router: Router) {}
  
    ngOnInit() {
        this.isLoading = true;
        this._studentListService.load()
        .subscribe(loadedStudents => {
            loadedStudents.forEach((studentObject) => {
            this.studentList.unshift(studentObject);
            });        
            this.isLoading = false;
          });
    	  }
      }
		
		</code>
  </pre>
</div>
</li>

 
</ul>
