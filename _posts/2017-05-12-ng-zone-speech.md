---
layout: post
title:  "Using NgZone to handle view updates"
date:   2017-05-12
categories: snippets
image: /images/ngzone.png
type: ng
author: Rachid Al Khayat
tags: 
    - angular
    - speech-recognition
    - speech
    - ng-zone
shortdesc: 	This is to show how to use zone.js to to handle view updates speech with the speech-recognition plugin
---
<ul class="tabs clearfix">
<li>
    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Preview</label>
    <div id="tab-content1" class="tab-content">
        <img src="/images/ngzone.png">
    </div>
</li>    
<li>
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">JavaScript</label>
    <div id="tab-content2" class="tab-content">
      <p>
      <pre class="language-javascript">
        <code>
import {Component, NgZone} from &#x27;@angular/core&#x27;;
import {SpeechRecognition, SpeechRecognitionTranscription,SpeechRecognitionOptions} from &#x27;nativescript-speech-recognition&#x27;;

@Component({
  moduleId: module.id,
  selector: &#x27;gf-main-ihm&#x27;,
  templateUrl: &#x27;main-ihm.html&#x27;
})

export class MainIhmComponent {
  speechOptions: SpeechRecognitionOptions;
  public textSpeech:string
  constructor(private speech:SpeechRecognition,
              private ngZone: NgZone,
              ) {
                
    &#x9;&#x9;this.speechOptions = {
                  locale: &#x27;fr-FR&#x27;,
                  onResult: (transcription: SpeechRecognitionTranscription)=&#x3E; {
                    this.ngZone.run(() =&#x3E; {
                               this.textSpeech = transcription.text;
                                console.log(&#x60;${transcription.text}&#x60;);
                                console.log(&#x60;${transcription.finished}&#x60;);
                      });
                  }
            };
  }

    writeText(){
      this.speech.available().then(result =&#x3E;{
        result ? this.startListening() : alert(&#x27;Speech recognition is not available&#x27;);
      }, error=&#x3E;{
        console.error(error);
      })
    }

    startListening(){
      this.speech.startListening(this.speechOptions).then(()=&#x3E; {
        console.log(&#x22;started listening&#x22;)
      }, error=&#x3E;{
        console.error(error)});
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
      <pre class="language-html">
        <code>
&#x3C;StackLayout &#x3E;
      &#x3C;Button text=&#x22;Talk &#x26;#xf130;&#x22;  
              class=&#x22;btn btn-primary main-btn main-btn-red font-awesome&#x22; 
              (tap)=&#x22;writeText()&#x22;&#x3E;
  &#x9;  &#x3C;/Button&#x3E;
      &#x3C;Label class=&#x22;gold card&#x22; 
             textWrap=&#x22;true&#x22; 
             [text]=&#x22;textSpeech&#x22;&#x3E;
  &#x9;  &#x3C;/Label&#x3E;
&#x3C;/StackLayout&#x3E;
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
@import &#x27;nativescript-theme-core/css/lemon.css&#x27;;


Page {
  background-color: #555555; 
}


.card {
    margin: 10;
    padding: 5;
    vertical-align:top;
    background-color: #D3D3D3;
    border-width: 1;
    border-radius: 5;
    border-color: #232323;
}


.gold {
    background-color: #F0E68C;
    border-width: 1;
    border-radius: 5;
    border-color: &#x9;#F0E68C;
}

.main-btn {
    border-width: 1;
    border-radius: 5;
    font-size: 26;
    height:120;

}

.main-btn-red {
    background-color: darkred;
    border-color: white;

}
.font-awesome {
    font-family: &#x22;FontAwesome&#x22;;
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
      
I want to add a little detail concerning using "Speech Recognition with NativeScript Angular" presented previously here: http://www.nativescriptsnacks.com/videos/2017/05/06/speech-recognition.html.
If we want to bind the "transcription text" with the label's text in the interface, the assignment shows inside an NgZone.
       
   </p>
</div>
</li>


</ul>
