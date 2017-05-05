---
layout: post
title:  "Using ngClass to color titles of newly added articles"
date:   2017-05-04
categories: snippets
image: /images/title_color.png
type: ng
author: Rachid Al Khayat
tags: 
    - angular
    - css
    - ngClass
shortdesc: 	This snippet shows how to use ngClass to set the style during a given condition
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/title_color.png">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">JavaScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-javascript">
        <code>
import {Component} from &#x27;@angular/core&#x27;;


@Component({
  moduleId: module.id,
  selector: &#x22;gf-list&#x22;,
  templateUrl: &#x22;list.html&#x22;
})
export class ListComponent implements OnInit {
  
  
  constructor() {}


&#x9;isNewDate(publishDate){
    &#x9;&#x9;const testedDate = new Date(publishDate);
    &#x9;&#x9;const nowDate = new Date();
    &#x9;&#x9;let timeDiff = Math.abs(nowDate.getTime() - testedDate.getTime());
    &#x9;&#x9;let diffDays = Math.ceil(timeDiff / (1000 * 3600 * 24)); 
  &#x9;&#x9;return (diffDays &#x3C; 14)
&#x9;}

  
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
      <pre class="language-html">
        <code>
&#x3C;StackLayout&#x3E;
       &#x3C;ListView [items]=&#x22;articles$ | async&#x22;&#x3E;
            &#x3C;template let-item=&#x22;item&#x22;&#x3E;                  
                &#x3C;GridLayout  columns=&#x22;*&#x22;&#x3E;

                    &#x3C;GridLayout columns=&#x22;auto,*,auto&#x22; rows=&#x22;*,*&#x22; col=&#x22;0&#x22; class=&#x22;card&#x22;&#x3E;
                        &#x3C;Image class=&#x22;m-5&#x22;     
                               horizontalAlignment=&#x22;left&#x22; 
                               rowSpan=&#x22;2&#x22; 
                               row=&#x22;0&#x22; 
                               col=&#x22;0&#x22; 
                               width=&#x22;100&#x22; height=&#x22;100&#x22;  
                              [src]=&#x22;item.imagepath.length&#x3E;0 ? item.imagepath : &#x27;~/assets/default.png&#x27;&#x22;&#x3E;
                        &#x3C;/Image&#x3E;
                        &#x3C;Label class=&#x22;m-5 h3&#x22;  
                               [ngClass]=&#x22;{newDate : isNewDate(item.date)}&#x22;  
                               class=&#x22;oldDate&#x22; 
                               col=&#x22;1&#x22; row=&#x22;0&#x22; 
                               [text]=&#x27;item.title&#x27;&#x3E;
                      &#x3C;/Label&#x3E;
                        &#x3C;Label class=&#x22;m-10 font-awesome&#x22;   style=&#x22;color:black;&#x22; col=&#x22;2&#x22;  row=&#x22;0&#x22; text=&#x27;&#x26;#xf15c;&#x27;&#x3E;&#x3C;/Label&#x3E;
                        &#x3C;Label class=&#x22;m-10 font-awesome h5&#x22; col=&#x22;1&#x22;  horizontalAlignment=&#x22;right&#x22; colSpan=&#x22;2&#x22; row=&#x22;1&#x22; [text]=&#x27;(item.date*-1) | date:&#x22;longDate&#x22;&#x27;&#x3E;&#x3C;/Label&#x3E;
                    &#x3C;/GridLayout&#x3E;                 
                &#x3C;/GridLayout&#x3E;
            &#x3C;/template&#x3E;
    &#x3C;/ListView&#x3E;
        </code>
    </pre>
   </p>
</div>
</li>

<li>
    <input type="radio" name="tabs" id="tab4" />
    <label for="tab4">CSS</label>
    <div id="tab-content4" class="tab-content">
      <p>
      <pre class="language-html">
        <code>
.oldDate {
    color:black
}
.newDate {
    color:red
}
        </code>
    </pre>
   </p>
</div>
</li>

<li>
    <input type="radio" name="tabs" id="tab5" />
    <label for="tab5">Notes</label>
    <div id="tab-content5" class="tab-content">
      <p>
      
In this snippet, I want to show how to use ngClass in Angular to set a style according to a certain condition. In this example, we have a list of articles, and if an article is published less than two weeks prior, their titles will appear in red.
       
   </p>
</div>
</li>


</ul>
