---
layout: page
title: Generador de contraseñas
permalink: /herramientas-de-seguridad/password-generator
intro_paragraph: >
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.5.3/vue.min.js"></script>
<script src="https://dl.dropboxusercontent.com/s/jnxv7j62cbxnusz/vue-pass.js"></script>

  <style type="text/css">
input[type=checkbox] {
	margin-right: 0;
}

.container {
	background-color: #23235B;
	box-shadow: 0px 2px 10px rgba(255, 255, 255, 0.2);
	padding: 20px;
	width: 350px;
	max-width: 100%;
}

.result-container {
	background-color: rgba(0, 0, 0, 0.4);
	display: flex;
	justify-content: flex-start;
	align-items: center;
	position: relative;
	font-size: 18px;
	letter-spacing: 1px;
	padding: 12px 10px;
	height: 50px;
	width: 100%;
}

.result-container #result {
  	word-wrap: break-word;
	max-width: calc(100% - 40px);
}

.result-container .btn {
	font-size: 20px;
	position: absolute;
	top: 5px;
	right: 5px;
	height: 40px;
	width: 40px;
}

.btn {
	border: none;
	color: #fff;
	cursor: pointer;
	font-size: 16px;
	padding: 8px 12px;
	background-color: #3B3B98;
}

.btn-large {
	display: block;
	width: 100%;
}

.setting {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin: 15px 0;
}

@media screen and (max-width: 400px) {
	.result-container {
		font-size: 14px;
	}
}

/* SOCIAL PANEL CSS */
.social-panel-container {
	position: fixed;
	right: 0;
	bottom: 80px;
	transform: translateX(100%);
	transition: transform 0.4s ease-in-out;
}

.social-panel-container.visible {
	transform: translateX(-10px);
}

.social-panel {	
	background-color: #fff;
	border-radius: 16px;
	box-shadow: 0 16px 31px -17px rgba(0,31,97,0.6);
	border: 5px solid #001F61;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	font-family: 'Muli';
	position: relative;
	height: 169px;	
	width: 370px;
	max-width: calc(100% - 10px);
}

.social-panel button.close-btn {
	border: 0;
	color: #97A5CE;
	cursor: pointer;
	font-size: 20px;
	position: absolute;
	top: 5px;
	right: 5px;
}

.social-panel button.close-btn:focus {
	outline: none;
}

.social-panel p {
	background-color: #001F61;
	border-radius: 0 0 10px 10px;
	color: #fff;
	font-size: 14px;
	line-height: 18px;
	padding: 2px 17px 6px;
	position: absolute;
	top: 0;
	left: 50%;
	margin: 0;
	transform: translateX(-50%);
	text-align: center;
	width: 235px;
}

.social-panel p i {
	margin: 0 5px;
}

.social-panel p a {
	color: #FF7500;
	text-decoration: none;
}

.social-panel h4 {
	margin: 20px 0;
	color: #97A5CE;	
	font-family: 'Muli';	
	font-size: 14px;	
	line-height: 18px;
	text-transform: uppercase;
}

.social-panel ul {
	display: flex;
	list-style-type: none;
	padding: 0;
	margin: 0;
}

.social-panel ul li {
	margin: 0 10px;
}

.social-panel ul li a {
	border: 1px solid #DCE1F2;
	border-radius: 50%;
	color: #001F61;
	font-size: 20px;
	display: flex;
	justify-content: center;
	align-items: center;
	height: 50px;
	width: 50px;
	text-decoration: none;
}

.social-panel ul li a:hover {
	border-color: #FF6A00;
	box-shadow: 0 9px 12px -9px #FF6A00;
}

.floating-btn {
	border-radius: 26.5px;
	background-color: #001F61;
	border: 1px solid #001F61;
	box-shadow: 0 16px 22px -17px #03153B;
	color: #fff;
	cursor: pointer;
	font-size: 16px;
	line-height: 20px;
	padding: 12px 20px;
	position: fixed;
	bottom: 20px;
	right: 20px;
	z-index: 999;
}

.floating-btn:hover {
	background-color: #ffffff;
	color: #001F61;
}

.floating-btn:focus {
	outline: none;
}

.floating-text {
	background-color: #001F61;
	border-radius: 10px 10px 0 0;
	color: #fff;
	font-family: 'Muli';
	padding: 7px 15px;
	position: fixed;
	bottom: 0;
	left: 50%;
	transform: translateX(-50%);
	text-align: center;
	z-index: 998;
}

.floating-text a {
	color: #FF7500;
	text-decoration: none;
}

@media screen and (max-width: 480px) {

	.social-panel-container.visible {
		transform: translateX(0px);
	}
	
	.floating-btn {
		right: 10px;
	}
}
  </style>

   <<!-- INSERT HTML HERE -->
<div class="container">
	<h2>Password Generator</h2>
	<div class="result-container">
		<span id="result"></span>
		<button class="btn" id="clipboard">
			<i class="far fa-clipboard"></i>
		</button>
	</div>
	<div class="settings">
		<div class="setting">
			<label>Password length</label>
			<input type="number" id="length" min='4' max='20' value='20' />
		</div>
		<div class="setting">
			<label>Include uppercase letters</label> 
			<input type="checkbox" id="uppercase" checked />
		</div>
		<div class="setting">
			<label>Include lowercase letters</label> 
			<input type="checkbox" id="lowercase" checked />
		</div>
		<div class="setting">
			<label>Include numbers</label> 
			<input type="checkbox" id="numbers" checked />
		</div>
		<div class="setting">
			<label>Include symbols</label> 
			<input type="checkbox" id="symbols" checked />
		</div>
	</div>
	<button class="btn btn-large" id="generate">
		Generate password
	</button>
</div>
  
