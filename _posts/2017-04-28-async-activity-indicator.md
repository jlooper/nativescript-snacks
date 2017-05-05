---
layout: post
title:  "Showing an ActivityIndicator with Observable async"
date:   2017-04-28
categories: snippets
image: /images/activity-indicator.gif
type: ng
author: Rachid Al Khayat
tags: 
    - async
    - observable
    - activity indicator
    - angular
shortdesc: 	How to use an ActivityIndicator with Observable async
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/activity-indicator.gif">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">JavaScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-javascript">
        <code>
ngOnInit(){
  this.isLoading= true;
  this.isAnonymous = BackendService.isAnonymous;
  this.sub$ = this.route.params;
  this.articles$ = this.sub$.switchMap((params: any) =&#x26;#x3E; {
                              this.categoryTitle = params[&#x26;#x27;categoryTitle&#x26;#x27;];
                              return &#x26;#x3C;any&#x26;#x3E;this.firebaseService.getArticleList(params[&#x26;#x27;id&#x26;#x27;])});&#x26;#x9;
 this.articles$.subscribe(()=&#x26;#x3E;{
           this.isLoading= false;
 });
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
&#x3C;ListView [items]=&#x22;articles$ | async&#x22;&#x3E;
            &#x3C;template let-item=&#x22;item&#x22;&#x3E;                  
                &#x3C;GridLayout&#x3E;
                    &#x3C;GridLayout columns=&#x22;auto,*,auto&#x22; class=&#x22;card&#x22;&#x3E;
                        &#x3C;Image class=&#x22;m-5&#x22; horizontalAlignment=&#x22;left&#x22; col=&#x22;0&#x22; width=&#x22;40&#x22; height=&#x22;40&#x22; [src]=&#x22;item.imagepath.length&#x3E;0 ? item.imagepath : &#x27;~/assets/camera.png&#x27;&#x22;&#x3E;&#x3C;/Image&#x3E;
                        &#x3C;Label class=&#x22;m-5&#x22;  (tap)=&#x22;viewDetail(item.id, categoryTitle)&#x22; col=&#x22;1&#x22; [text]=&#x27;item.title&#x27;&#x3E;&#x3C;/Label&#x3E;
                        &#x3C;Label class=&#x22;m-10 font-awesome&#x22;   style=&#x22;color:black;&#x22; col=&#x22;2&#x22; text=&#x27;&#x26;#xf15c;&#x27;&#x3E;&#x3C;/Label&#x3E;
                    &#x3C;/GridLayout&#x3E;                 
                &#x3C;/GridLayout&#x3E;
            &#x3C;/template&#x3E;
    &#x3C;/ListView&#x3E;
    &#x3C;StackLayout class=&#x22;dimmer&#x22; visibility=&#x22;{{isLoading ? &#x27;visible&#x27; : &#x27;collapsed&#x27;}}&#x22;&#x3E;
               &#x3C;GridLayout rows=&#x22;*&#x22; visibility=&#x22;{{isLoading ? &#x27;visible&#x27; : &#x27;collapsed&#x27;}}&#x22;&#x3E;
                       &#x3C;ActivityIndicator [busy]=&#x22;isLoading&#x22; [visibility]=&#x22;isLoading ? &#x27;visible&#x27; : &#x27;collapse&#x27;&#x22; row=&#x22;1&#x22; horizontalAlignment=&#x22;center&#x22; verticalAlignment=&#x22;center&#x22;&#x3E;&#x3C;/ActivityIndicator&#x3E;    
               &#x3C;/GridLayout&#x3E;
    &#x3C;/StackLayout&#x3E;
        </code>
    </pre>
   </p>
</div>
</li>


</ul>
