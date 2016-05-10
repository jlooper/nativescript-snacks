---
layout: post
title:  "Create an Inset List"
date:   2016-04-13
categories: snippets
author: Burke Holland
image: /images/inset-list.png
tags: 
    - snippet
    - inset list
    - list
shortdesc: Burke Holland's Inset List. 
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/inset-list.png">
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
 &lt;grid-layout columns=&quot;*&quot;&gt;
  &lt;list-view items=&quot;{{ fakeListItems }}&quot; class=&quot;listview&quot;&gt;
      &lt;list-view.itemTemplate&gt;
          &lt;stack-layout class=&quot;item&quot; col=&quot;0&quot; class=&quot;item&quot;&gt;
              &lt;label text=&quot;{{ artist + &apos;: &apos; + title }}&quot; col=&quot;1&quot;/&gt;
          &lt;/stack-layout&gt;
      &lt;/list-view.itemTemplate&gt;
  &lt;/list-view&gt;
&lt;/grid-layout&gt;
        </code>
      </pre>
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">CSS</label>
    <div id="tab-content3" class="tab-content">
      <pre class="language-css">
        <code>
        .background-color-light {
        background-color: #ffffff; }

        .background-color-accent {
        background-color: #FF404B; }

        .background-color-dark {
        background-color: #243044; }

        .color-light {
        color: black; }

        .color-accent {
        color: #FF404B; }

        .color-dark {
        color: #243044; }

        .action-bar-light {
        background-color: #ffffff;
        color: #FF404B; }

        navigation-button {
        color: #FF404B; }

        .action-bar-accent {
        background-color: #FF404B;
        color: white; }

        .action-bar-dark {
        background-color: #243044;
        color: white; }

        .h1 {
        font-size: 36;
        margin-bottom: 10; }

        .h2 {
        font-size: 30;
        margin: 10 0 10 0; }

        .h3 {
        font-size: 24;
        margin: 10 0 10 0; }

        .h4 {
        font-size: 18;
        margin: 10 0 10 0; }

        .h5 {
        font-size: 14;
        margin: 10 0 10 0; }

        .h6 {
        font-size: 12;
        margin: 10 0 10 0; }

        .p {
        font-size: 14;
        margin: 0 0 10 0; }

        .background-color-light {
        background-color: #ffffff; }

        .background-color-accent {
        background-color: #FF404B; }

        .background-color-dark {
        background-color: #243044; }

        .color-light {
        color: black; }

        .color-accent {
        color: #FF404B; }

        .color-dark {
        color: #243044; }

        .button {
        padding: 10 12 10 10;
        min-width: 52;
        border-radius: 2; }
        .button .button-accent {
            background-color: #FF404B;
            color: #ffffff; }
            .button .button-accent .button-outline {
            background-color: #ffffff;
            color: #FF404B;
            border-color: #FF404B;
            border-width: 1; }

        .button-full {
        padding: 0; }

        .button-small {
        padding: 2 4 1 4;
        min-width: 28;
        min-height: 30;
        font-size: 12; }

        .button-large {
        padding: 0 16 0 16;
        min-width: 68;
        min-height: 59;
        font-size: 20; }

        .button-light {
        background-color: #ffffff;
        color: #FF404B;
        border-color: #b2b2b2;
        border-width: 1; }

        .button-dark {
        background-color: #243044;
        color: #ffffff; }
        .button-dark .button-outline {
            color: #243044;
            border-color: #243044;
            border-width: 1; }

        .listview {
        color: black; }
        .listview .item {
            padding: 10 10 10 10;
            font-size: 16;
            color: #444; }
            .listview .item .h2 {
            margin: 0;
            margin: 0;
            font-size: 20; }
            .listview .item .p {
            font-size: 14;
            color: #666;
            margin: 0; }

        .listview-inset {
        margin: 10;
        border-width: 1;
        border-color: #DDDDDD;
        border-radius: 10; }

        .item-avatar image {
        border-radius: 25;
        width: 50;
        height: 50; }

        .item-avatar stacklayout, .item-thumbnail stacklayout {
        padding-left: 16; }

        .form {
        margin: 0 0 20 0;
        padding: 0; }
        .form .button {
            margin: 0 0 0 10;
            padding: 0; }
        .form switch {
            margin-right: 16; }
        .form .form-item {
            padding: 10 16 10 16; }
        .form .input {
            padding-top: 2; }
        .form .input-inset {
            background-color: #EEEEEE;
            border-radius: 2;
            padding: 8; }
        .form .input-label {
            font-size: 18;
            padding: 4 0 5 0;
            color: #444; }

        .form-inset {
        margin: 10;
        border-width: 1;
        border-color: #DDDDDD; }

        .background-color-light {
        background-color: #ffffff; }

        .background-color-accent {
        background-color: #FF404B; }

        .background-color-dark {
        background-color: #243044; }

        .color-light {
        color: black; }

        .color-accent {
        color: #FF404B; }

        .color-dark {
        color: #243044; }

        .switch-accent {
        background-color: #FF404B; }

        .switch-dark {
        background-color: #243044; }

        .background-color-light {
        background-color: #ffffff; }

        .background-color-accent {
        background-color: #FF404B; }

        .background-color-dark {
        background-color: #243044; }

        .color-light {
        color: black; }

        .color-accent {
        color: #FF404B; }

        .color-dark {
        color: #243044; }

        .slider-light {
        background-color: #ffffff; }

        .slider-accent {
        background-color: #FF404B; }

        .slider-dark {
        background-color: #243044; }

        .background-color-light {
        background-color: #ffffff; }

        .background-color-accent {
        background-color: #FF404B; }

        .background-color-dark {
        background-color: #243044; }

        .color-light {
        color: black; }

        .color-accent {
        color: #FF404B; }

        .color-dark {
        color: #243044; }

        .segmented-bar {
        height: 50; }
        .segmented-bar .segmnted-bar-light {
            background-color: #ffffff; }
        .segmented-bar .segmented-bar-accent {
            background-color: #FF404B;
            color: #ffffff; }
        .segmented-bar .segmented-bar-dark {
            background-color: #243044;
            color: #ffffff; }

        textfield {
        font-size: 14; }

        .fa {
        font-family: 'FontAwesome', FontAwesome; }

        .fa-large {
        font-family: 'FontAwesome', FontAwesome;
        font-size: 26; }

        .padding {
        padding: 10; }

        .edges {
        margin-left: 10;
        margin-right: 10; }

        .left {
        horizontal-align: left;
        text-align: left; }

        .right {
        text-align: right;
        horizontal-align: right; }

        .center {
        horizontal-align: center;
        text-align: center; }

        .hr {
        height: 1;
        background-color: #CDCDCD; }

        .debug {
        border-width: 1;
        border-color: red; }

        </code>
      </pre>
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab4" />
    <label for="tab4">JavaScript</label>
    <div id="tab-content4" class="tab-content">
      <pre class="language-javascript">
        <code>import { ObservableArray } from 'data/observable-array';
        import { Observable, EventData } from 'data/observable';
        import { Page } from 'ui/page';

        let viewModel = new Observable({
            fakeListItems: new ObservableArray([
                { artist: 'Anberlin', title: 'New Surrender', img: 'new-surrender.jpg' },
                { artist: 'Anberlin', title: 'Vital', img: 'vital.jpg' },
                { artist: 'Anberlin', title: 'Dark Is The Way, Light Is A Place', img: 'dark-is-the-way.jpg' },
                { artist: 'Anberlin', title: 'Lowborn', img: 'lowborn.jpg' },
                { artist: 'Anberlin', title: 'Cities', img: 'cities.jpg' },
                { artist: 'Anberlin', title: 'Lost Songs', img: 'lost-songs.jpg' },
                { artist: 'Anberlin', title: 'Never Take Friendship Personal', img: 'never-take-friendship-personal.jpg' },
                { artist: 'Anberlin', title: 'Blueprints for City Friendships: The Anberlin Anthology', img: 'blueprints-for-city-friendships.jpg' },
                { artist: 'Anberlin', title: 'Blueprints for The Black Market', img: 'blueprints-for-the-blackmarket.jpg' },
                { artist: 'Anberlin', title: 'Dancing Between The Fibers Of Time', img: 'dancing-between-the-fibers-of-time.jpg' },
                { artist: 'Anberlin', title: 'Devotion', img: 'devotion.jpg' },
                { artist: 'Anberlin', title: 'Vital (The Remixes)', img: 'vital-the-remixes.jpg' }
            ])
        });

        class SimpleListView extends BasePage {
            loaded(args: EventData) {
            args.object.bindingContext = viewModel;
            }
        }

        module.exports = new SimpleListView();</code>
      </pre>
    </div>
  </li>
</ul>
