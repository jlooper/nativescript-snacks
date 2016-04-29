---
layout: post
title:  "CSS Keyframe-based animations"
date:   2016-04-29
categories: snippets
image: /images/keyframe-animations.gif
tags: 
    - css
    - keyframe
    - animation
shortdesc: Beautiful CSS-based animations using keyframes. 
---
<ul class="tabs clearfix">
  <li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/keyframe-animations.gif">
    </div>
  </li>
  <li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">XML</label>
    <div id="tab-content2" class="tab-content">
      <pre class="language-html">
        <code>
 &#x3C;Page xmlns=&#x22;http://www.nativescript.org/tns.xsd&#x22;
        xmlns:mainpage=&#x22;views/main-page&#x22;
        class=&#x22;qsf-page&#x22;
        backgroundSpanUnderStatusBar=&#x22;true&#x22;
        ios:actionBarHidden=&#x22;true&#x22;&#x3E; 
                            
                &#x3C;GridLayout id=&#x22;intro-elements&#x22;&#x3E;
                    &#x3C;GridLayout id=&#x22;intro-background&#x22; class=&#x22;intro-background-intro&#x22; backgroundColor=&#x22;#151F2F&#x22; originY=&#x22;0&#x22; /&#x3E;
                    &#x3C;GridLayout id=&#x22;intro-logo-bg&#x22; class=&#x22;intro-logo-bg-intro&#x22; backgroundColor=&#x22;#3C5AFD&#x22; width=&#x22;93&#x22; height=&#x22;93&#x22; horizontalAlignment=&#x22;center&#x22; verticalAlignment=&#x22;center&#x22; borderRadius=&#x22;20&#x22; scaleX=&#x22;18&#x22; scaleY=&#x22;18&#x22; /&#x3E;
                    &#x3C;GridLayout id=&#x22;intro-logo-n&#x22; class=&#x22;intro-logo-n-intro&#x22; backgroundImage=&#x22;res://logo&#x22; width=&#x22;93&#x22; height=&#x22;93&#x22; horizontalAlignment=&#x22;center&#x22; verticalAlignment=&#x22;center&#x22; /&#x3E;
                    &#x3C;GridLayout id=&#x22;intro-logo-ns&#x22; class=&#x22;intro-logo-ns-intro&#x22; backgroundImage=&#x22;res://logo_text&#x22; width=&#x22;199&#x22; height=&#x22;31&#x22; horizontalAlignment=&#x22;center&#x22; verticalAlignment=&#x22;center&#x22; margin=&#x22;160 0 0 0&#x22; /&#x3E;

                    &#x3C;Label id=&#x22;intro-text-one&#x22;
                            class=&#x22;intro-text-one-intro&#x22;
                            text=&#x22;Build truly&#x26;#xA;native apps with&#x26;#xA;JavaScript&#x22;
                            fontSize=&#x22;37&#x22;
                            horizontalAlignment=&#x22;center&#x22;
                            verticalAlignment=&#x22;center&#x22;
                            textWrap=&#x22;true&#x22;
                            color=&#x22;white&#x22;
                            textAlignment=&#x22;center&#x22; /&#x3E;
                    &#x3C;Label id=&#x22;intro-text-two&#x22;
                            class=&#x22;intro-text-two-intro&#x22;
                            text=&#x22;Develop native cross platform&#x26;#xA;apps from a single code base&#x22;
                            fontSize=&#x22;19&#x22;
                            horizontalAlignment=&#x22;center&#x22;
                            verticalAlignment=&#x22;center&#x22;
                            textWrap=&#x22;true&#x22;
                            color=&#x22;#8DA1AB&#x22;
                            textAlignment=&#x22;center&#x22; /&#x3E;

                    &#x3C;Button id=&#x22;intro-get-started&#x22;
                            class=&#x22;intro-get-started-intro&#x22;
                            text=&#x22;GET STARTED&#x22;
                            backgroundColor=&#x22;#1DBE67&#x22;
                            color=&#x22;white&#x22;
                            borderRadius=&#x22;25&#x22;
                            height=&#x22;50&#x22;
                            width=&#x22;234&#x22;
                            fontSize=&#x22;18&#x22;
                            tap=&#x22;tapGetStarted&#x22;/&#x3E;
                    &#x3C;Label id=&#x22;intro-version&#x22;
                            class=&#x22;intro-version-intro&#x22;
                            text=&#x22;version 2.0.0&#x22;
                            fontSize=&#x22;14&#x22;
                            horizontalAlignment=&#x22;center&#x22;
                            verticalAlignment=&#x22;center&#x22;
                            color=&#x22;white&#x22;
                            textAlignment=&#x22;center&#x22; /&#x3E;
                &#x3C;/GridLayout&#x3E;
&#x3C;/Page&#x3E;
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
@keyframes intro-background-enter {
    0% { transform: scale(1, 1); }
    22.4% { transform: scale(1, 1); }
    46.77% { transform: scale(1, 0); }
    100% { transform: scale(1, 0); }
}

@keyframes intro-logo-bg-intro {
    0% {
        transform: scale(18, 18), translate(0, 0);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
    }
    21.25% {
        transform: scale(1, 1), translate(0, -60);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
    }
    22% {
        transform: scale(0, 0), translate(0, -60);
        opacity: 0;
    }
    100% {
        transform: scale(0, 0), translate(0, -60);
        opacity: 0;
    }
}
@keyframes intro-logo-bg-enter {
    0% {
        transform: scale(0, 0), translate(0, -60);
        opacity: 0;
    }
    100% {
        transform: scale(0, 0), translate(0, -60);
        opacity: 0;
    }
}

@keyframes intro-logo-n-intro {
    0% {
        transform: translate(0, 0);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
        opacity: 0;
    }
    21% {
        transform: translate(0, -60);
        opacity: 1;
    }
    30% {
        transform: translate(0, -60);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
        opacity: 1;
    }
    51% { transform: scale(0.56, 0.56), translate(0, -205); }
    100% { transform: scale(0.56, 0.56), translate(0, -205); }
}
@keyframes intro-logo-n-enter {
    0% {
        transform: scale(0.56, 0.56), translate(0, -205);
        opacity: 1;
    }
    24% {
        transform: scale(0.56, 0.56), translate(0, -205);
        opacity: 0;
    }
    100% {
        transform: scale(0.56, 0.56), translate(0, -205);
        opacity: 0;
    }
}

@keyframes intro-logo-ns-intro {
    0% {
        opacity: 0;
        transform: translate(0, 80);
    }
    9.25% {
        opacity: 0;
        transform: translate(0, 80);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
    }
    30% {
        opacity: 1;
        transform: translate(0, -60);
    }
    32% {
        opacity: 1;
        transform: translate(0, -60);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
    }
    53% {
        opacity: 1;
        transform:  scale(0.56, 0.56), translate(0, -240);
    }
    100% {
        opacity: 1;
        transform:  scale(0.56, 0.56), translate(0, -240);
    }
}
@keyframes intro-logo-ns-enter {
    0% {
        transform:  scale(0.56, 0.56), translate(0, -240);
        opacity: 1;
    }
    24% {
        transform:  scale(0.56, 0.56), translate(0, -240);
        opacity: 0;
    }
    100% {
        transform:  scale(0.56, 0.56), translate(0, -240);
        opacity: 0;
    }
}

@keyframes intro-text-one-intro {
    0% {
        opacity: 0;
        transform: translate(0, 210);
    }
    40.5% {
        opacity: 0;
        transform: translate(0, 210);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
    }
    62% {
        opacity: 1;
        transform: translate(0, -55);
    }
    100% {
        opacity: 1;
        transform: translate(0, -55);
    }
}
@keyframes intro-text-one-enter {
    0% {
        opacity: 1;
        transform: translate(0, -55);
    }
    53.6% {
        opacity: 1;
        transform: translate(0, -55);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
    }
    100% {
        opacity: 0;
        transform: translate(0, 20);
    }
}

@keyframes intro-text-two-intro {
    0% {
        opacity: 0;
        transform: translate(0, 280);
    }
    47.5% {
        opacity: 0;
        transform: translate(0, 280);
        animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
    }
    66.25% {
        opacity: 1;
        transform: translate(0, 70);
    }
    100% {
        opacity: 1;
        transform: translate(0, 70);
    }
}
@keyframes intro-text-two-enter {
    0% {
        opacity: 1;
        transform: translate(0, 70);
    }
    48.8% {
        opacity: 1;
        transform: translate(0, 70);
    }
    91.2% {
        opacity: 0;
        transform: translate(0, 300);
    }
    100% {
        opacity: 0;
        transform: translate(0, 300);
    }
}

@keyframes intro-get-started-intro {
    0% {
        opacity: 0;
        transform: translate(0, 175);
    }
    66.25% {
        opacity: 0;
        transform: translate(0, 175);
    }
    86.75% {
        opacity: 1;
        transform: translate(0, 175);
    }
}
@keyframes intro-get-started-enter {
    0% {
        opacity: 1;
        transform: translate(0, 175);
    }
    12% {
        opacity: 1;
        transform: translate(0, 175);
    }
    75.2% {
        opacity: 0;
        transform: translate(0, 300);
    }
    100% {
        opacity: 0;
        transform: translate(0, 300);
    }
}

@keyframes intro-version-intro {
    0% {
        opacity: 0;
        transform: translate(0, 260);
    }
    88.25% {
        opacity: 0;
        transform: translate(0, 260);
    }
    100% {
        opacity: 0.8;
        transform: translate(0, 260);
    }
}
@keyframes intro-version-enter {
    0% {
        opacity: 0.8;
        transform: translate(0, 260);
    }
    12% {
        opacity: 0;
        transform: translate(0, 260);
    }
    75.2% {
        opacity: 0;
        transform: translate(0, 260);
    }
    100% {
        opacity: 0;
        transform: translate(0, 260);
    }
}

.intro-logo-bg-intro {
    animation-name: intro-logo-bg-intro;
    animation-duration: 4;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-logo-n-intro {
    animation-name: intro-logo-n-intro;
    animation-duration: 4;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-logo-ns-intro {
    animation-name: intro-logo-ns-intro;
    animation-duration: 4;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-text-one-intro {
    animation-name: intro-text-one-intro;
    animation-duration: 4;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-text-two-intro {
    animation-name: intro-text-two-intro;
    animation-duration: 4;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-get-started-intro {
    animation-name: intro-get-started-intro;
    animation-duration: 4;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-version-intro {
    animation-name: intro-version-intro;
    animation-duration: 4;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}

.intro-background-enter {
    animation-name: intro-background-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-logo-bg-enter {
    animation-name: intro-logo-bg-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-logo-n-enter {
    animation-name: intro-logo-n-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-logo-ns-enter {
    animation-name: intro-logo-ns-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-text-one-enter {
    animation-name: intro-text-one-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-text-two-enter {
    animation-name: intro-text-two-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-get-started-enter {
    animation-name: intro-get-started-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}
.intro-version-enter {
    animation-name: intro-version-enter;
    animation-duration: 1.25;
    animation-fill-mode: forwards;
    animation-iteration-count: 1;
    animation-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1);
}

@keyframes example-odd-enter {
    0% {
        opacity: 0;
        transform: translate(-200, 0);
    }
    100% {
        opacity: 1;
        transform: translate(0, 0);
    }
}
@keyframes example-even-enter {
    0% {
        opacity: 0;
        transform: translate(200, 0);
    }
    100% {
        opacity: 1;
        transform: translate(0, 0);
    }
}


        </code>
      </pre>
    </div>
  </li>
</ul>
