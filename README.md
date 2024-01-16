# Atomic-Structure
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Structure of Atom </title>
    <link rel="stylesheet" href="atomic.css">
  <style>
    body {
	margin: 0;
	padding: 0;
	width: 100vw;
	height: 100vh;
	overflow: hidden;
	display: flex;
	align-items: center;
	justify-content: center;
	background: repeating-conic-gradient(#FFF4 0%, transparent .0002%, transparent .075%, transparent .65%), repeating-conic-gradient(#FFF2 0%, transparent .0004%, transparent 0.05%, transparent .495%), radial-gradient(circle at 50% 50%, #121212, #000);
	perspective: 100vmin;
}

body * {
	transform-style: preserve-3d;
}

*::before {
	box-sizing: border-box;
}

h1 {
	position: absolute;
	top: 4vmin;
	color: #fff;
	font-family: Arial, serif;
	font-weight: normal;
	font-size: 3.5vmin;
	margin: 0;
}

.atom {
	width: 50vmin;
	height: 50vmin;
	display: flex;
	align-items: center;
	justify-content: center;
	border-radius: 100%;
	transition: 0.4s ease 0s;
	cursor: zoom-in;
}

.atom:active {
	transform: scale3d(1.5,1.5,1.5);
}

.atom:before {
	content: "";
	width: 50vmin;
	height: 50vmin;
	position: absolute;
	background: radial-gradient(#913ab7 -50%, #fff0 50%);
	transform: translateZ(-6vmin);
	box-shadow: 
		0 0 5vmin -2vmin #cddc3920, 0 0 10vmin 0vmin #cddc3920, 
		0 0 10vmin 0vmin #39dcbe20, 0 0 10vmin 0 #cddc3920 inset, 
		0 0 25vmin 0 #39dcbe20 inset;
	border-radius: 100%;
	animation: orbit-cloud 3s ease 0s infinite alternate;
	opacity: 0.25;
}

@keyframes orbit-cloud {
	0% { filter: hue-rotate(0deg); }
	100% { filter: hue-rotate(50deg);}
}



/*** NUCLEOUS ***/

.nucleous {
	width: 16vmin;
	height: 16vmin;
	display: flex;
	align-items: center;
	justify-content: center;
	border-radius: 100%;
}

.row {
	border-radius: 100%;
	transform: rotateX(80deg);
	position: absolute;
	width: 40%;
	height: 40%;
	margin-top: -8vmin;
	left: 33%;
	display: flex;
	align-items: center;
	justify-content: center;
	transform: rotateX(80deg) rotate(180deg);
	animation: orbit-nucleous 3s linear 0s infinite;
}

.row:nth-child(1) div:before {
	content: "";
	position: absolute;
	width: 100%;
	height: 100%;
	border-radius: 100%;
	margin-top: -11vmin;
	background: red;
	background: radial-gradient(circle at 40% 60%, #fff0, 3vmin, #00000040 calc(3vmin + 1px) 100%), radial-gradient(circle at 28% 57%, #fff, 0.3vmin, #fff0 calc(0.3vmin + 1px) 100%), radial-gradient(circle at 37% 71%, #fff, 0.5vmin, #fff0 calc(0.5vmin + 1px) 100%), radial-gradient(circle at 40% 60%, var(--c2), 1.65vmin, #fff0 calc(1.65vmin + 1px) 100%) var(--c1);
}

.row:nth-child(2) {
	--znt: 1.3,1.3,1.3;
	margin-top: 0vmin;
	animation: orbit-nucleous3 3s linear 0s infinite;
}


@keyframes orbit-nucleous {
	0% { transform: rotateX(80deg) rotate(0deg); }
	100% { transform: rotateX(80deg) rotate(360deg);}
}

@keyframes orbit-nucleous3 {
	0% { transform: rotateX(80deg) rotate(0deg) scale3d(var(--znt)); }
	100% { transform: rotateX(80deg) rotate(360deg) scale3d(var(--znt)); }
}

.row div {
	--c1: #bc0003;
	--c2: #fa0001;
	width: 6vmin;
	height: 6vmin;
	border: 1px solid #0006;
	border-radius: 100%;
	background: 
		radial-gradient(circle at 40% 60%, #fff0, 3vmin, #00000040 calc(3vmin + 1px) 100%), 
		radial-gradient(circle at 28% 57%, #fff, 0.3vmin, #fff0 calc(0.3vmin + 1px) 100%), 
		radial-gradient(circle at 37% 71%, #fff, 0.5vmin, #fff0 calc(0.5vmin + 1px) 100%), 
		radial-gradient(circle at 40% 60%, var(--c2), 1.65vmin, #fff0 calc(1.65vmin + 1px) 100%) 
		var(--c1);
	position: absolute;
	top: -3vmin;
	animation: orbit-nucleous-particle 3s linear 0s infinite;
}

@keyframes orbit-nucleous-particle {
	0% { transform: rotateX(90deg) rotateY(360deg) scale3d(0.75, 0.75, 0.75); }
	100% { transform: rotateX(90deg) rotateY(0deg) scale3d(0.75, 0.75, 0.75);}
}

.row div.neutron {
	--c1: #082976;
	--c2: #124b9c;
}

.row div:nth-child(2) {
	top: calc(100% - 3vmin);
}

.row div:nth-child(3) {
	left: -3vmin;
	top: calc(50% - 3vmin);
}

.row div:nth-child(4) {
	left: calc(100% - 3vmin);
	top: calc(50% - 3vmin);
}



/*** ELECTRONS ***/

.orbits {
	position: absolute;
	width: 100%;
	height: 100%;
	border-radius: 100%;
	animation: orbit-spin 180s linear 0s infinite;
}

@keyframes orbit-spin {
	0% { transform: rotate(0deg); }
	100% { transform: rotate(360deg);}
}

.orbits:before, .orbits:after {
	content: "";
	position: absolute;
	width: 100%;
	height: 100%;
	border-radius: 100%;
	animation: orbit-spin 180s linear 0s infinite;
	border: 0.2vmin dotted #CDDC3980;
	filter: blur(1px);
	opacity: 0.5;
}

.orbits:after {
	width: 60%;
	height: 60%;
	top: 20%;
	left: 20%;
	animation-direction: reverse;
	animation-duration: 90s;
}

.electron {
	--pos: rotateY(0deg);
	--tim: 2s;
	position: absolute;
	width: 100%;
	height: 100%;
	box-shadow: -10px 5px 3px -5px #CDDC3920 inset, 10px 0px 3px -5px #CDDC3920;
	border-radius: 100%;
	transition: all 0.4s ease 0s;
	transform: rotateX(80deg) rotate(180deg);
	animation: orbit-electron var(--tim) linear calc(var(--tim) * -0.5) infinite;
}

@keyframes orbit-electron {
	0% { transform: rotateX(80deg) var(--pos) rotate(0deg); }
	100% { transform: rotateX(80deg) var(--pos) rotate(-360deg);}
}

.electron:before {
	--c1: #8BC34A;
	--c2: #CDDC39;
	width: 1vmin;
	height: 1vmin;
	content: "";
	position: absolute;
	border-radius: 100%;
	box-shadow: 0 0 9px 0px #CDDC39;
	border: 1px solid #fff8;
	left: calc(50% - 0.5vmin);
	top: -0.5vmin;
	background: 
		radial-gradient(circle at 40% 60%, #fff0, 3vmin, #00000040 calc(3vmin + 1px) 100%), 
		radial-gradient(circle at 45% 73%, #fff, 0.3vmin, #fff0 calc(0.3vmin + 1px) 100%), 
		radial-gradient(circle at 27% 58%, #fff, 0.5vmin, #fff0 calc(0.5vmin + 1px) 100%), 
		radial-gradient(circle at 40% 60%, var(--c2), 1vmin, #fff0 calc(1vmin + 1px) 100%), var(--c1);
	transform: rotateX(90deg);
	animation: orbit-electron-particle var(--tim) linear 0s infinite;
}

@keyframes orbit-electron-particle {
	0% { transform: rotateX(90deg) rotateY(-360deg); }
	100% { transform: rotateX(90deg) rotateY(0deg);}
}

.electron:nth-child(2) {
	--pos: rotateY(70deg);
	--tim: 1.535s;
}

.electron:nth-child(3) {
	--pos: rotateY(40deg);
	--tim: 1.875s;
}

.electron:nth-child(4) {
	--pos: rotateY(110deg);
	--tim: 1.275s;
}

.electron:nth-child(n+5) {
	width: 67%;
	height: 67%;
	left: 18%;
	top: 18%;
}

.electron:nth-child(5) {
	--pos: rotateY(140deg);
	--tim: 1.125s;
}

.electron:nth-child(6) {
	--pos: rotateY(25deg);
	--tim: 1s;
}



/*** INFO ***/

.info {
	position: absolute;
	width: 98vw;
	height: 60vmin;
	z-index: -1;
	font-family: Arial, serif;
	display: flex;
	align-items: center;
	justify-content: center;
}

.inner-shell, .outer-shell, .inner-nucleous {
	width: 20.5vmin;
	height: 12vmin;
	position: absolute;
	display: flex;
	align-items: center;
	justify-content: flex-end;
	opacity: 0.05;
	top: 40vmin;
	color: #fff;
	margin-right: 80vmin;
}

.inner-shell {
	margin-top: 0.95vmin;
}

.outer-shell {
	top: 10vmin;
	margin-right: 83.5vmin;
}

.info > div:before {
	content: "";
	position: absolute;
	width: 15vmin;
	height: 15vmin;
	border: 0.25vmin solid #fff0;
	border-left: 0.25vmin dotted #fff;
	border-radius: 100% 0 0 0;
	transform: rotate(-45deg);
	right: -25vmin;
	margin-top: -33vmin;
}

.info > div.outer-shell:before {
	transform: rotate(0deg);
	margin-top: 2vmin;
	right: -30vmin;
	height: 25vmin;
	width: 25vmin;
	clip-path: polygon(0 50%, 100% 100%, 100% 100%, 0% 98%);
}

.inner-nucleous {
	margin-left: 83vmin;
	margin-right: 0 !important;
	top: 19vmin !important;
	height: 17.5vmin !important;
}

.inner-nucleous:before {
	transform: rotate(155deg) !important;
	left: -34.125vmin;
	margin-top: 11vmin !important;
}

.inner-shell:after, .outer-shell:after, .inner-nucleous:after {
	content: "";
	position: absolute;
	width: 15vmin;
	height: 0;
	right: -14.5vmin;
	margin-top: -18vmin;
	z-index: 333;
	border-top: 0.25vmin dotted #fff;
	transform: rotate(-23deg);
}

.outer-shell:after {
	right: -6vmin;
	margin-top: 13.1vmin;
	transform: rotate(14deg);
	width: 6vmin;
}

.inner-nucleous:after {
	transform: rotate(0deg);
	left: -21.5vmin;
	margin-top: 2.75vmin;
	width: 21.5vmin;
}


.info-particle {
	position: absolute;
	width: 20vmin;
	height: 11.5vmin;
	left: 0;
	top: 0;
	border: 0.25vmin dotted #fff;
	border-radius: 0.2vmin;
}

.inner-nucleous .info-particle {
	height: 17.25vmin;
}

.inner-shell:hover,
.outer-shell:hover,
.inner-nucleous:hover{
	opacity: 1;
}



h3 {
	margin: 1vmin 0 1.25vmin;
	font-size: 1.9vmin;
	font-weight: normal;
	text-align: center;
	border-bottom: 0.25vmin dotted #fff;
	padding-bottom: 0.75vmin;
}

p {
	text-align: left;
	font-weight: normal;
	margin: 1vmin 0 3vmin -2.75vmin;
	font-size: 1.5vmin;
	padding-left: 5vmin;
}

p strong {
	font-size: 2.5vmin;
}

p:before {
	--c1: #8BC34A;
	--c2: #CDDC39;
	content: "\2212";
	position: absolute;
	width: 3vmin;
	height: 3vmin;
	border-radius: 100%;
	margin-left: -3.85vmin;
	background: radial-gradient(circle at 45% 45%, var(--c2), 1vmin, #fff0 calc(1vmin + 5px) 100%), var(--c1);
	box-shadow: 0 0 0.5vmin 0 #fff, 0 0 0.1vmin 0.15vmin #fff;
	color: #222;
	text-shadow: 1px 1px 2px #fff, -1px 1px 2px #fff, 1px -1px 2px #fff, -1px -1px 2px #fff;
	font-size: 3vmin;
	line-height: 3.15vmin;
	text-align: center;
}

p:after {
	content: "( NEGATIVE CHARGE )";
	position: absolute;
	bottom: -1.5vmin;
	left: 0;
	font-size: 1vmin;
	width: 100%;
	text-align: center;
}

.inner-nucleous p:before {
	--c1: #bc0003;
	--c2: #fa0001;
	content: "+";
}

.inner-nucleous p + p:before {
	--c1: #082976;
	--c2: #124b9c;
	content: "";
}

.inner-nucleous p:after {
	content: "( POSITIVE CHARGE )";
}
.inner-nucleous p + p:after {
	content: "( NO CHARGE )";
}


body:has(.outer-shell:hover) .atom .orbits .electron:nth-child(n+5),
body:has(.outer-shell:hover) .atom .nucleous {
	opacity: 0.15;
}

body:has(.inner-shell:hover) .atom .orbits .electron:nth-child(-n+4),
body:has(.inner-shell:hover) .atom .nucleous {
	opacity: 0.15;
}

body:has(.inner-nucleous:hover) .atom .orbits .electron {
	opacity: 0.15;
}

.show-info:hover + .info > div {
	opacity: 0.9;
}

.show-info {
	position: absolute;
	bottom: 4vmin;
	font-size: 3.5vmin;
	color: #fff;
	font-weight: bold;
	border: 0.25vmin solid #ffffffc9;
	width: 5vmin;
	height: 5vmin;
	display: flex;
	align-items: center;
	justify-content: center;
	border-radius: 100%;
}

.show-info:hover {
	color: #111;
	background: #fff;
	border-color: #111;
}


/*** PORTRAIT ***/

@media only screen and (orientation: portrait) {

	.info {
		height: 98vh;
	}

	.inner-nucleous {
		margin-left: 0vmin !important;
		margin-right: 0 !important;
		top: calc(50% + 32vmin) !important;
	}

	.inner-nucleous:before {
		transform: rotate(247deg) !important;
		left: -1.125vmin;
		margin-top: -75vmin !important;
	}

	.inner-nucleous:after {
		transform: rotate(90deg);
		left: -1.5vmin;
		margin-top: -41.25vmin;
		width: 23vmin;
	}

	h3 {
		font-size: 2.5vmin;
	}

	p {
		font-size: 2vmin;
	}

	p:after {
		font-size: 1.65vmin;
	}

	.info > div.outer-shell {
		margin-top: calc(50vh - 53.5vmin);
		margin-right: 47.5vmin;
	}

	.outer-shell:after {
		right: -4.5vmin;
		margin-top: 17.75vmin;
		transform: rotate(60deg);
	}

	.info > div.outer-shell:before {
		transform: rotate(52deg);
		margin-top: 33vmin;
		right: -28vmin;
	}

	.info > div.inner-shell {
		margin-right: -36vmin;
		margin-top: calc(50vh - 84vmin);
	}
	
	.inner-shell:after {
		width: 14vmin;
		right: 15.25vmin;
		margin-top: 25vmin;
		transform: rotate(105deg);
	}
	
	.inner-shell:before {
		transform: rotate(80deg) !important;
		right: 14vmin !important;
		margin-top: 51vmin !important;
	}

}
  </style>
</head>
<body>
    <h1>Carbon</h1>
<div class="atom">
	<div class="nucleous">
		<div class="row">
			<div class="proton"></div>
			<div class="proton"></div>
			<div class="neutron"></div>
			<div class="neutron"></div>
		</div>
		<div class="row">
			<div class="neutron"></div>
			<div class="neutron"></div>
			<div class="proton"></div>
			<div class="proton"></div>
		</div>
	</div>
	<div class="orbits">
		<div class="electron"></div>
		<div class="electron"></div>
		<div class="electron"></div>
		<div class="electron"></div>
		<div class="electron"></div>
		<div class="electron"></div>
	</div>
</div>
<div class="show-info">i</div>
<div class="info">
	<div class="inner-shell">			
		<div class="info-particle">
			<h3>INNER SHELL</h3>
			<p><strong>2</strong> ELECTRONS</p>
		</div>
	</div>
	<div class="outer-shell">
		<div class="info-particle">
			<h3>OUTER SHELL</h3>
			<p><strong>4</strong> ELECTRONS</p>
		</div>
	</div>
	<div class="inner-nucleous">
		<div class="info-particle">
			<h3>NUCLEOUS</h3>
			<p><strong>6</strong> PROTONS</p>
			<p><strong>6</strong> NEUTRONS</p>
		</div>
	</div>
</div>

  <script src='https://cdnjs.cloudflare.com/ajax/libs/matter-js/0.19.0/matter.min.js'></script>
</body>
</html>
