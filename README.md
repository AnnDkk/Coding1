# Coding One-Final project 
The Persistence-by Ann
## Introduction
This project shapes multiple three-dimensional rotating Spaces through multiple processing of 2D images and 3D Spaces. At the same time, the interactive sound bed and ethereal music are combined to create a sense of fatalism of infinite reincarnation.

## Documentation
JavaScript
MIMIC：https://mimicproject.com/code/f30862bd-cab5-84e1-a098-2e919f3616cc

## Code Application
* maxiOsc
>Create sound waves by creating four oscillators with cosine and sine functions. Then the mouse x and y values are obtained for acoustic interaction.

```
   var changeThis = 1;
   var maximJs = maximilian();
   var maxiAudio = new maximJs.maxiAudio();
   
   maxiAudio.init();
    var osc1 = new maximJs.maxiOsc();
    var osc2 = new maximJs.maxiOsc();
    var osc3 = new maximJs.maxiOsc();
    var osc4 = new maximJs.maxiOsc();
    var drawOutput = new Array(1024);
    var counter = 0;
```
>Using mouse position to control sound allows users to have a better interactive experience
```
maxiAudio.play = function() {
        var wave = osc1.sinewave(98 + (osc2.sinewave(10) * 20)) * osc3.sinewave(0.01*mouseX) + osc4.sinewave(88 + (osc2.sinewave(1) * 5)) * osc3.sinewave(0.01);
  var wave1 = osc1.sinewave(98 + (osc2.sinewave(10) * 20)) * osc3.sinewave(0.01*mouseY/20) + osc4.sinewave(88 + (osc2.sinewave(1) * 5)) * osc3.sinewave(0.01);
        counter++;
        drawOutput[counter % 1024] = wave;
        return wave * 0.4;
};
```


* maxiClock
>Use the sequencing clock to change the beat to adjust the audio playback rate.
```
 var counter = 0;
  let maxi = maximilian();
  let audio = new maxi.maxiAudio();
  let mySample = new maxi.maxiSample();
  var myClock = new maxi.maxiClock();
  let ticks = 4;
  audio.init();
  audio.loadSample('apple.wav',mySample); 
function song(){
  var out = 0;
  var a = myClock.playHead+1;
    myClock.ticker();
  
  if (myClock.tick) {
            
    			console.log(a);
        }
    out += mySample.play(1);
    
    return out ;
  }
  audio.play = function() {

      return song();
       
	}
```

* Three.js 
>The geometry in Three.js is applied to shape the overall spatial form.
Combined with the geometry of the app library, I made my own texture material.

<img src="https://github.com/AnnDkk/Coding1/blob/main/beijing11.png" width="300" height="300">         <img src="https://github.com/AnnDkk/Coding1/blob/main/beijing12.png" width="300" height="300">          <img src="https://github.com/AnnDkk/Coding1/blob/main/beijing123.png" width="300" height="300">





