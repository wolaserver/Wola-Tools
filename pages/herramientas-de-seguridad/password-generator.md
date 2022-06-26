---
layout: page
title: Generador de contraseñas
permalink: /herramientas-de-seguridad/password-generator
intro_paragraph: >
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.5.3/vue.min.js"></script>


  <style type="text/css">
    .wrapper {
  width: 400px;
  max-width: 100%;
  min-height: 400px;
  margin: 40px auto;
  position: relative;
  border: 1px solid #eee;
  border-radius: 3px;
  padding: 40px 20px;
  font-size: 0.85em;
  -webkit-box-shadow: 0 0 15px 0 rgba(0, 0, 0, 0.05);
  box-shadow: 0 0 15px 0 rgba(0, 0, 0, 0.05);
  background-color: #f4f7fc;
  position: relative;
  transition: all ease-in 0.25s;
}
h1 {
  text-align: center;
  margin: 0 0 40px;
}
.field-wrap {
  margin-bottom: 20px;
}
form {
  overflow: overlay;
  margin-top: 30px;
}
label {
  display: inline-block;
  min-width: 20%;
}
.range-slider_wrapper {
  position: relative;
  width: 100%;
  margin: 10px 0 30px;
}
.range-slider {
  -webkit-appearance: none;
  appearance: none;
  background: #9fd2fa;
  width: 100%;
  border-radius: 3px;
  vertical-align: bottom;
  margin: 0;
  height: 6px;
  cursor: pointer;
  transition: all ease-in 0.25s;
}
.range-slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  border-radius: 0;
  border: 0;
  position: relative;
  width: 4px;
  height: 15px;
  background-color: #2799f3;
}
.range-slider::-moz-range-thumb {
  -moz-appearance: none;
  appearance: none;
  border-radius: 0;
  border: 0;
  position: relative;
  width: 4px;
  height: 15px;
  background-color: #2799f3;
}
.range-slider:focus {
  outline: none;
}
.range-slider:hover::-webkit-slider-thumb, .range-slider:active::-webkit-slider-thumb {
  top: 0px;
}
::-moz-range-track {
  background: transparent;
  border: 0;
}
input::-moz-focus-inner, input::-moz-focus-outer {
  border: 0;
}
.range-value {
  text-transform: capitalize;
  float: right;
  vertical-align: bottom;
  min-width: 30px;
  display: inline-block;
  text-align: center;
  border-radius: 3px;
  font-size: 0.9em;
}
.slider-bar {
  position: absolute;
  height: 6px;
  border-top-left-radius: 3px;
  border-bottom-left-radius: 3px;
  background: #3fa4f4;
  left: 0;
  bottom: 0;
  pointer-events: none;
}
.slider-strength .range-slider {
  cursor: default;
}
.slider-strength .slider-bar {
  border-radius: 3px;
  transition: all ease-in 0.25s;
}
.slider-strength .range-slider::-webkit-slider-thumb {
  background-color: transparent;
}
.slider-strength .range-slider::-moz-range-thumb {
  background-color: transparent;
}
.slider-strength.weak .range-slider {
  background-color: white;
}
.slider-strength.weak .slider-bar, .slider-strength.weak .slider-bar:after {
  background-color: #ff6666;
}
.slider-strength.average .range-slider {
  background-color: #ffd699;
}
.slider-strength.average .slider-bar, .slider-strength.average .slider-bar:after {
  background-color: #ff9800;
}
.slider-strength.strong .range-slider {
  background-color: #d5e9bd;
}
.slider-strength.strong .slider-bar, .slider-strength.strong .slider-bar:after {
  background-color: #8BC34A;
}
.slider-strength.secure .range-slider {
  background-color: #d5e9bd;
}
.slider-strength.secure .slider-bar, .slider-strength.secure .slider-bar:after {
  background-color: #8BC34A;
}
.password-box {
  width: 100%;
  min-height: 80px;
  margin-bottom: 40px;
  position: relative;
  text-align: center;
  border-radius: 3px;
  background: #fff;
  letter-spacing: 2px;
  transition: all ease-in 0.3s;
  border: 1px solid #bdcce6;
}
.password-box .password {
  width: 70%;
  padding: 1.5em 1em;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  word-wrap: break-word;
}
.regenerate-password, .copy-password {
  width: 44px;
  height: 50%;
  position: absolute;
  right: 0;
  transition: all ease-in 0.25s;
}
.regenerate-password:hover, .copy-password:hover {
  opacity: 0.8;
}
.regenerate-password {
  top: 0;
  background-color: #fff;
  background-image: url('https://nourabusoud.github.io/password-genie/images/regenerate.svg');
  background-size: 40%;
  background-position: center center;
  background-repeat: no-repeat;
  transition: all ease-in 0.25s;
  cursor: pointer;
}
.regenerate-password:hover {
  background-color: #fff;
}
.copy-password {
  bottom: 0;
  background-color: #fff;
  background-image: url('https://nourabusoud.github.io/password-genie/images/copy-full.svg');
  background-size: 50%;
  background-position: center center;
  background-repeat: no-repeat;
  transition: all ease-in 0.25s;
  cursor: pointer;
}
.copy-password:hover {
  background-color: #fff;
}
.tooltip {
  font-size: 0.8em;
  display: block;
  text-align: center;
  padding: 0.5em;
  border-radius: 3px;
  position: absolute;
  bottom: -35px;
  left: 50%;
  transform: translateX(-50%);
}
.seperator {
  width: 100%;
  height: 3px;
  background-color: #fff;
  margin: 60px 0 40px;
}
/* Footer */
footer {
  width: 100%;
  text-align: center;
  color: #fff;
}
footer a {
  color: #fff;
}
.github-links {
  margin-bottom: 30px;
}
textarea, textarea:focus {
  font-size: 16px;
}

  </style>

 <div id="app">
    <section class="wrapper">   
      <h1>The Password Genie</h1>
      <div class="password-box">
        <span id="password" class="password" v-on:click="copyToClipboard">{{ password }}</span>
        <span class="regenerate-password" v-on:click="generatePassword"></span>
        <span class="copy-password" v-on:click="copyToClipboard"></span>
        <span class="tooltip" v-if="copied">Password copied successfuly!</span>
      </div>
      <form @keydown.enter.prevent="">
        <div class="field-wrap">
          <label>Strength</label>
          <span class="range-value">{{strength.text}}</span>
          <div class="range-slider_wrapper slider-strength" v-bind:class="strength.text">
            <span class="slider-bar" v-bind:style="{ width: strength.score + '%' }"></span>
            <input type="range" class="range-slider" min="0" max="100" v-model="strength.score" disabled>
          </div>  
        </div>
        <div class="seperator"></div>
        <div class="field-wrap">
          <label>Length</label>
          <span class="range-value">{{settings.length}}</span>
          <div class="range-slider_wrapper">
            <span class="slider-bar" v-bind:style="{ width: lengthThumbPosition + '%' }"></span>
            <input type="range" class="range-slider" min="6" v-bind:max="settings.maxLength" v-model="settings.length">
          </div>  
        </div>
        <div class="field-wrap">  
          <label>Digits</label>
          <span class="range-value">{{settings.digits}}</span>
          <div class="range-slider_wrapper">
            <span class="slider-bar"  v-bind:style="{ width: digitsThumbPosition + '%' }"></span>
            <input type="range" class="range-slider" min="0" v-bind:max="settings.maxDigits" v-model="settings.digits">
          </div>  
        </div>
        <div class="field-wrap">  
          <label>Symbols</label>
          <span class="range-value">{{settings.symbols}}</span>
          <div class="range-slider_wrapper">
            <span class="slider-bar"  v-bind:style="{ width: symbolsThumbPosition + '%' }"></span>
            <input type="range" class="range-slider" min="0" v-bind:max="settings.maxSymbols" v-model="settings.symbols">
          </div>  
        </div>
      </form>
    </section>
  </div>

  <script>
  	new Vue({
  el: '#app',
  data() {
    return {
      password: '',
      copied: false,
      settings: {
        maxLength: 64,
        maxDigits: 10,
        maxSymbols: 10,
        length: 12,
        digits: 4,
        symbols: 2,
        ambiguous: true,
      }
    };
  },
  computed: {
    lengthThumbPosition: function() {
      return (( (this.settings.length - 6) / (this.settings.maxLength - 6)) * 100);
    },
    digitsThumbPosition: function() {
      return (( (this.settings.digits - 0) / (this.settings.maxDigits - 0)) * 100);
    },
    symbolsThumbPosition: function() {
      return (( (this.settings.symbols - 0) / (this.settings.maxSymbols - 0)) * 100);
    },
    strength: function() {
      var count = {
        excess: 0,
        upperCase: 0,
        numbers: 0,
        symbols: 0
      };


      var weight = {
        excess: 3,
        upperCase: 4,
        numbers: 5,
        symbols: 5,
        combo: 0, 
        flatLower: 0,
        flatNumber: 0
      };

      var strength = {
        text: '',
        score: 0
      };

      
      var baseScore = 30;

      for (i=0; i < this.password.length;i++){
        if (this.password.charAt(i).match(/[A-Z]/g)) {count.upperCase++;}
        if (this.password.charAt(i).match(/[0-9]/g)) {count.numbers++;}
        if (this.password.charAt(i).match(/(.*[!,@,#,$,%,^,&,*,?,_,~])/)) {count.symbols++;} 
      }
      
      count.excess = this.password.length - 6;
      
      if (count.upperCase && count.numbers && count.symbols){
        weight.combo = 25; 
      }
      else if ((count.upperCase && count.numbers) || (count.upperCase && count.symbols) || (count.numbers && count.symbols)){
        weight.combo = 15; 
      }
      
      if (this.password.match(/^[\sa-z]+$/))
      { 
        weight.flatLower = -30;
      }
      
      if (this.password.match(/^[\s0-9]+$/))
      { 
        weight.flatNumber = -50;
      }

      var score = 
        baseScore + 
        (count.excess * weight.excess) + 
        (count.upperCase * weight.upperCase) + 
        (count.numbers * weight.numbers) + 
        (count.symbols * weight.symbols) + 
        weight.combo + weight.flatLower + 
        weight.flatNumber;

      if(score < 30 ) {
        strength.text = "weak";
        strength.score = 10;
        return strength;
      } else if (score >= 30 && score < 75 ){
        strength.text = "average";
        strength.score = 40;
        return strength;
      } else if (score >= 75 && score < 150 ){
        strength.text = "strong";
        strength.score = 75;
        return strength;
      } else {
        strength.text = "secure";
        strength.score = 100;
        return strength;
      }
    },
  },
  mounted() {
    this.generatePassword();
  },
  watch: {
    settings: {
      handler: function() {
        this.generatePassword();
      },
      deep: true
    }
  },
  methods: {
    // copy password to clipboard
    copyToClipboard(){
      // we should create a textarea, put the password inside it, select it and finally copy it
      var copyElement = document.createElement("textarea");
      copyElement.style.opacity = '0';
      copyElement.style.position = 'fixed';
      copyElement.textContent = this.password;
      var body = document.getElementsByTagName('body')[0];
      body.appendChild(copyElement);
      copyElement.select();
      document.execCommand('copy');
      body.removeChild(copyElement);
      
      this.copied = true;
      // reset this.copied
      setTimeout(() => {
        this.copied = false;
      }, 750);
    },
    // generate the password
    generatePassword() {
      var lettersSetArray = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"];
      var symbolsSetArray = [ "=","+","-","^","?","!","%","&","*","$","#","^","@","|"];
      //var ambiguousSetArray = ["(",")","{","}","[","]","(",")","/","~",";",":",".","<",">"];
      var passwordArray = [];
      var digitsArray = [];
      var digitsPositionArray = [];


      // first, fill the password array with letters, uppercase and lowecase
      for (var i = 0; i < this.settings.length; i++) {
        // get an array for all indexes of the password array
        digitsPositionArray.push(i);

        var upperCase = Math.round(Math.random() * 1);
        if (upperCase === 0) {
          passwordArray[i] = lettersSetArray[Math.floor(Math.random()*lettersSetArray.length)].toUpperCase();
        }
        else {
          passwordArray[i] = lettersSetArray[Math.floor(Math.random()*lettersSetArray.length)];
        }
      }

      // Add digits to password
      for (i = 0; i < this.settings.digits; i++) {
        digit = Math.round(Math.random() * 9);
        numberIndex = digitsPositionArray[Math.floor(Math.random()*digitsPositionArray.length)];

        passwordArray[numberIndex] =  digit;

        /* remove position from digitsPositionArray so we make sure to the have the exact number of digits in our password
        since without this step, numbers may override other numbers */

        var j = digitsPositionArray.indexOf(numberIndex);
        if(i != -1) {
          digitsPositionArray.splice(j, 1);
        }
      }

      // add special charachters "symbols"
      for (i = 0; i < this.settings.symbols; i++) {
        var symbol = symbolsSetArray[Math.floor(Math.random()*symbolsSetArray.length)];
        var symbolIndex = digitsPositionArray[Math.floor(Math.random()*digitsPositionArray.length)];

        passwordArray[symbolIndex] =  symbol;

        /* remove position from digitsPositionArray so we make sure to the have the exact number of digits in our password
        since without this step, numbers may override other numbers */

        var j = digitsPositionArray.indexOf(symbolIndex);
        if(i != -1) {
          digitsPositionArray.splice(j, 1);
        }
      }
      this.password = passwordArray.join("");
    },
  },
});
  </script>
