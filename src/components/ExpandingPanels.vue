<template>
    <div class="container">
        <div v-for="(panel, index) in panels" :key="index" :class="{ 'panel': true, 'active': index === activeIndex }" :style="{ 'background-image': 'url(' + panel.image + ')' }">
            <h3>{{ panel.title }}</h3>
        </div>
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
export default {
  data() {
    return {
      panels: [
        { title: 'Explore the World', image: 'https://images.unsplash.com/photo-1558979158-65a1eaa08691?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80' },
        { title: 'Wild Forest', image: 'https://images.unsplash.com/photo-1572276596237-5db2c3e16c5d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80' },
        { title: 'Sunny Beach', image: 'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1353&q=80' },
        { title: 'City on Winter', image: 'https://images.unsplash.com/photo-1551009175-8a68da93d5f9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1351&q=80' },
        { title: 'Mountains - Clouds', image: 'https://images.unsplash.com/photo-1549880338-65ddcdfd017b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80' },
      ],
      activeIndex: 0, // Set the initial active index
    };
  },

mounted() {
    const panels = document.querySelectorAll('.panel');
    const social_panel_container = document.querySelector('.social-panel-container');
    const floating_btn = document.querySelector('.floating-btn');
    const close_btn = document.querySelector('.close-btn');

    panels.forEach((panel, index) => {
      panel.addEventListener('click', () => {
        this.activeIndex = index;
      });
    });

    floating_btn.addEventListener('click', () => {
    social_panel_container.classList.toggle('visible');
    });

    close_btn.addEventListener('click', () => {
    social_panel_container.classList.remove('visible');
    });
  },
};
</script>
<style scoped>

body {
	display: flex;
	align-items: center;
	justify-content: center;
	font-family: 'Muli', sans-serif;
	height: 100vh;
	margin: 0;
}

.container {
	display: flex;
	width: 90vw;
}

.panel {
	background-size: auto 100%;
	background-position: center;
	background-repeat: no-repeat;
	border-radius: 50px;
	color: #fff;
	flex: 0.5;
	cursor: pointer;
	height: 80vh;
	position: relative;
	margin: 10px;
	transition: flex 0.7s cubic-bezier(0.05, 0.6, 0.4, 0.9);
}

.panel h3 {
	font-size: 24px;
	opacity: 0;
	position: absolute;
	bottom: 20px;
	left: 20px;
	margin: 0;
	transition: opacity 0s ease-in 0s;
}

.panel.active {
	flex: 5;
}

.panel.active h3 {
	opacity: 1;
	transition: opacity 0.3s ease-in 0.4s;
}


@media screen and (max-width: 480px) {
	.container {
		width: 100vw;
	}
	
	.panel:nth-of-type(4) {
		display: none;
	}
	
	.panel:nth-of-type(5) {
		display: none;
	}
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