


<template>
  <div class="panda">
    <div class="ear left"></div>
    <div class="ear right"></div>
    <div class="eye left">
      <div class="eye-roll"></div>
    </div>
    <div class="eye right">
      <div class="eye-roll"></div>
    </div>
    <div class="nose">
      <i class="fa fa-heart"></i>
    </div>
    <div class="mouth"></div>
  </div>
  <div class="social-panel-container">
    <div class="social-panel">
      <button class="close-btn"><i class="fas fa-times"></i></button>
      <h4>ENTRE EM CONTATO</h4>
      <ul>
        <li>
          <a href="https://www.linkedin.com/in/stefane-santos-2296421a8" target="_blank">
            <img
              src="@/assets/icons/icons8-linkedin.svg"
              style="width: 50px"
            />
          </a>
        </li>
        <li>
          <a href="https://github.com/StefaneSantos45" target="_blank">
              <img
              src="@/assets/icons/icons8-github.svg"
              style="width: 50px"
            />
          </a>
        </li>
        <li>
          <a href="https://instagram.com/Ohster_" target="_blank">
             <img
              src="@/assets/icons/icons8-instagram.svg"
              style="width: 50px"
            />
          </a>
        </li>
      </ul>
    </div>
  </div>
  <button class="floating-btn">CONTATO</button>
</template>

<script>
document.addEventListener('DOMContentLoaded', (event) => {
  const eyes = document.querySelectorAll('.eye-roll');

  window.addEventListener('mousemove', (e) => {
    eyes.forEach(eye => {
      const x = eye.getBoundingClientRect().left + (eye.clientWidth / 2);
      const y = eye.getBoundingClientRect().top + (eye.clientHeight / 2);
      const radian = Math.atan2(e.pageX - x, e.pageY - y);
      const rot = (radian * (180 / Math.PI) * -1) + 90;
      eye.style.transform = `rotate(${rot}deg)`;
      
      console.log(rot);
    });
  });

const social_panel_container = document.querySelector('.social-panel-container');
const floating_btn = document.querySelector('.floating-btn');
const close_btn = document.querySelector('.close-btn');

floating_btn.addEventListener('click', () => {
  social_panel_container.classList.toggle('visible');
});

close_btn.addEventListener('click', () => {
  social_panel_container.classList.remove('visible');
});
});
</script>
<style >
body {
	background-color: #fafafa;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	height: 100vh;
	margin: 0;
}
.panda {
	background-color: #fff;
	border-radius: 50%;
	position: relative;
	height: 170px;
	width: 170px;
}
.panda .ear {
	background-color: #000;
	border-radius: 50%;
	position: absolute;
	top: 5px;
	height: 50px;
	width: 50px;
	z-index: -1;
}
.panda .ear.left {
	left: 0;
}
.panda .ear.right {
	right: 0;
}
.panda .eye {
	background-color: #000;
	position: absolute;
	top: 50px;
	left: 50%;
	height: 50px;
	width: 40px;
}
.panda .eye.left {
	border-radius: 100% 60% 80% 60%;	
	transform: translateX(calc(-50% - 35px));
}
.panda .eye.right {
	border-radius: 60% 100% 60% 80%;	
	transform: translateX(calc(-50% + 35px));
}
.panda .eye .eye-roll {
	background: #fff;
	border-radius: 50%;
	position: absolute;
	top: 20px;
	left: 20px;
	height: 12px;
	width: 12px;
	transform-origin: center left;
}
.panda .nose {
	position: absolute;
	top: 55%;
	left: 50%;
	transform: translate(-50%);
}
.panda .mouth {
	background: transparent;
	border-radius: 0 0 50% 50%;
	border: 2px solid transparent;
	border-bottom: 2px solid #000;
	position: absolute;
	top: 45%;
	left: 50%;
	transform: translate(-50%);
	height: 50px;
	width: 50px;
}
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
	border: 5px solid #899ecb;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	font-family: 'Muli';
	position: relative;
	height: 151px;	
	width: 264px;
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
	background-color: #899ecb;
	border: 1px solid #899ecb;
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

