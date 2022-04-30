<template>
	<div class="page">
		<div class="container">
		<div class="main-left">
			<header class="header">
				<div class="row">
					<div class="col-sm-12 offset-sm-0 col-md-10 offset-md-1">
						<div class="header__info">
							<div class="header__title">
								<p>Паша Костенников</p>
							</div>
						</div>
					</div>
				</div>
			</header>

			<main class="main">
				<section class="stack">
					<div class="row">
						<div class="col-sm-12 offset-sm-0 col-md-10 offset-md-1">
							<div class="info">
								<div class="info__title">
									<h1>Занимаюсь фронтенд разработкой с 2018</h1>
								</div>
								<div class="info__technologies">
									<p>
										<span>[</span>html<span>]</span>
									</p>
									<p>
										<span>[</span>css<span>]</span>
									</p>
									<p>
										<span>[</span>scss<span>]</span>
									</p>
									<p>
										<span>[</span>bootstrap<span>]</span>
									</p>
									<p>
										<span>[</span>js<span>]</span>
									</p>
									<p>
										<span>[</span>jquery<span>]</span>
									</p>
									<p>
										<span>[</span>pug<span>]</span>
									</p>
									<p>
										<span>[</span>vue.js<span>]</span>
									</p>
									<p>
										<span>[</span>react<span>]</span>
									</p>
									<p>
										<span>[</span>type script<span>]</span>
									</p>
								</div>
							</div>
						</div>
					</div>
				</section>
				<section class="project" @click="add" v-for="(project, index) in left" :key="index">
					<div class="row">
						<div class="col-sm-4 offset-sm-0 col-md-4 offset-md-1 project__left">
							<div class="project__website">
								<div class="project__website-title">
									<h5>{{ project.title }}</h5>
								</div>
								<div class="project__website-description">
									<h5>{{ project.date }}</h5>
								</div>
							</div>
						</div>
						<div class="col-sm-6 offset-sm-0 col-md-6 project__right">
							<div class="project__stack">
								<div class="project__stack-img" v-for="(technology, index) in project.technologies" :key="index">
									<div :class="'form-' +`${technology.name.toLowerCase()}`" v-html="technology.svg"></div>
									<div class="project__stack-text">
										<p>{{ technology.name }}</p>
									</div>
								</div>
							</div>
						</div>
					</div>
					<div class="popper" v-if="popover">

						<div class="popper__left" @click.stop="clickOutside">

						</div>
						<div class="popper__right" @click.stop="clickInside">
							<div class="header">
								<div class="header__info" :class="{'header__popover': popover === true, }">
									<div class="header__links">
										<div class="row">
											<div class="col-sm-7 offset-sm-0 col-md-7 offset-md-1">
												<a href="#">kostennikov.ru</a>
											</div>

											<div class="col-sm-2 offset-sm-0 col-md-2 offset-md-1 header__close">
												<p class="header__button" @click.stop="close" @mouseover.stop="mouseOver" v-if="!over">[ххххххх]</p>
												<p class="header__button-over" @click.stop="close" @mouseleave="mouseLeave" v-if="over">[закрыть]</p>
											</div>
										</div>
									</div>
								</div>
							</div>
							<div class="main">
								<img src="./assets/img/ava.png" alt="">

							</div>
						</div>

					</div>
				</section>
			</main>

			<footer class="footer">
				<div class="row">
					<div class="col-10 offset-1">
						<div class="footer__img">
							<img src="./assets/img/ava.png" alt="">
						</div>
					</div>
				</div>
			</footer>
		</div>

		<div class="main-right">
			<header class="header">
				<div class="header__info">
					<div class="header__links">
						<div class="row">
							<div class="col-sm-5 offset-sm-0 col-md-5 offset-md-1">
								<a href="mailto:pavel.kostennikov@gmail.com">pavel.kostennikov@gmail.com</a>
							</div>

							<div class="col-sm-5 offset-sm-0 col-md-5 offset-md-1">
								<a href="https://t.me/kostennikov" target="_blank">телеграм</a>
							</div>
						</div>
					</div>
				</div>
			</header>

			<main class="main">
				<section class="project" v-for="(project, index) in rightProjects" :key="index">
					<div class="row">
						<div class="col-sm-4 offset-sm-0 col-md-4 offset-md-1 project__left">
							<div class="project__website">
								<div class="project__website-title">
									<h5>{{ project.title }}</h5>
								</div>
								<div class="project__website-description">
									<h5>{{ project.date }}</h5>
								</div>
							</div>
						</div>
						<div class="col-sm-6 offset-sm-0 col-md-6 project__right">
							<div class="project__stack">
								<div class="project__stack-img" v-for="(technology, index) in project.technologies" :key="index">
									<div :class="'form-' +`${technology.name.toLowerCase()}`" v-html="technology.svg"></div>

									<div class="project__stack-text">
										<p>{{ technology.name }}</p>
									</div>
								</div>
							</div>
						</div>
					</div>
				</section>
			</main>

			<footer class="footer">
				<div class="row">
					<div class="col-10 offset-1">
						<div class="info">
							<div class="info__title">
								<h1>Всегда открыт к новому.
									Если хотите поработать со мной, пишите на почту или в телеграм.</h1>
							</div>
							<div class="info__description">
								<p>Сайт нарисован
									<a href="https://tugolukovskiy.com/" target="_blank">Ярославом Туголуковским</a></p>
							</div>

						</div>
					</div>
				</div>
			</footer>
		</div>

	</div>
	</div>
</template>

<script>

export default {
	name: "App",

	data() {
		return {
			left: [
				{
					title: 'Сайт Ярослава Туголуковского',
					description: 'Сайт для души',
					date: '2021-2022',
					technologies: [
						{
							svg: this.html,
							name: 'HTML'
						},
						{
							svg: this.scss,
							name: 'CSS'
						},
						{
							svg: this.jquery,
							name: 'JQuery'
						},
						{
							svg: this.bootstrap,
							name: 'Bootstrap'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
						{
							svg: this.mobile,
							name: 'Mobile'
						},
					]
				},
				{
					title: 'Колорлон',
					description: 'Сайт для бабла',
					date: '2021',
					technologies: [
						{
							svg: this.pug,
							name: 'Pug'
						},
						{
							svg: this.scss,
							name: 'SCSS'
						},
						{
							svg: this.js,
							name: 'JavaScript'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
					]
				},
				{
					title: 'Acer',
					description: 'Сайт для бабла',
					date: '2021',
					technologies: [
						{
							svg: this.pug,
							name: 'Pug'
						},
						{
							svg: this.scss,
							name: 'SCSS'
						},
						{
							svg: this.js,
							name: 'JavaScript'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
						{
							svg: this.mobile,
							name: 'Mobile'
						},
					]
				},
				{
					title: 'Madeleine',
					description: 'Сайт для бабла',
					date: '2021',
					technologies: [
						{
							svg: this.pug,
							name: 'Pug'
						},
						{
							svg: this.scss,
							name: 'SCSS'
						},
						{
							svg: this.jquery,
							name: 'JQuery'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
						{
							svg: this.mobile,
							name: 'Mobile'
						},
					]
				},
				{
					title: 'Fonar.tv',
					description: 'Сайт для бабла',
					date: '2020-2022',
					technologies: [
						{
							svg: this.html,
							name: 'HTML'
						},
						{
							svg: this.scss,
							name: 'SCSS'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
						{
							svg: this.mobile,
							name: 'Mobile'
						},
					]
				},
				{
					title: 'CRM Sijeko',
					description: 'Сайт для бабла',
					date: '2020',
					technologies: [
						{
							svg: this.vue,
							name: 'Vue'
						},
					]
				},
			],
			popover: false,
			over: false,
			leave: false,

			leftProjects: [],
			rightProjects: [],
			html: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">\n' +
							'\t\t\t\t\t\t\t\t\t\t<path d="M17.7274 5.47018C18.3865 3.50313 18.7161 2.5196 19.3273 1.79245C19.8671 1.15034 20.5603 0.653305 21.3433 0.346938C22.23 0 23.2722 0 25.3564 0H183.644C185.728 0 186.77 0 187.657 0.346938C188.44 0.653305 189.133 1.15034 189.673 1.79245C190.284 2.5196 190.613 3.50313 191.273 5.47018L207.848 54.9404C208.477 56.8176 208.792 57.7563 208.917 58.7165C209.028 59.5686 209.028 60.4314 208.917 61.2835C208.792 62.2437 208.477 63.1824 207.848 65.0596L191.273 114.53C190.613 116.497 190.284 117.48 189.673 118.208C189.133 118.85 188.44 119.347 187.657 119.653C186.77 120 185.728 120 183.644 120H25.3564C23.2722 120 22.23 120 21.3433 119.653C20.5603 119.347 19.8671 118.85 19.3273 118.208C18.7161 117.48 18.3865 116.497 17.7274 114.53L1.15158 65.0596C0.522563 63.1824 0.208053 62.2437 0.0831348 61.2835C-0.0277116 60.4314 -0.0277116 59.5686 0.0831348 58.7165C0.208053 57.7563 0.522563 56.8176 1.15158 54.9404L17.7274 5.47018Z" fill="#F9C4AD"/>\n' +
							'\t\t\t\t\t\t\t\t\t</svg>`,
			htmlStroke: `<svg width="209" height="120" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M18.6756 5.78788C19.3619 3.73989 19.6335 2.98235 20.0928 2.43592C20.5248 1.92206 21.0799 1.52381 21.7077 1.27819C22.3761 1.01666 23.1872 1 25.3564 1H183.644C185.813 1 186.624 1.01666 187.292 1.27819C187.92 1.52381 188.475 1.92206 188.907 2.43593C189.367 2.98235 189.638 3.73989 190.324 5.78788L206.9 55.2581C207.541 57.1716 207.816 58.004 207.925 58.8456C208.025 59.612 208.025 60.388 207.925 61.1545C207.816 61.996 207.541 62.8284 206.9 64.7419L190.324 114.212C189.638 116.26 189.367 117.018 188.907 117.564C188.475 118.078 187.92 118.476 187.292 118.722C186.624 118.983 185.813 119 183.644 119H25.3564C23.1872 119 22.3761 118.983 21.7077 118.722C21.0799 118.476 20.5248 118.078 20.0928 117.564C19.6335 117.018 19.3619 116.26 18.6756 114.212L2.09977 64.7419C1.45861 62.8284 1.18425 61.996 1.07478 61.1544C0.975074 60.388 0.975074 59.612 1.07478 58.8456C1.18425 58.004 1.45861 57.1716 2.09977 55.2581L18.6756 5.78788Z" stroke="#AEC1BF" stroke-width="2"/>
<path d="M79.9574 53H81.8374V58.94H89.0774V53H90.9574V67H89.0774V60.66H81.8374V67H79.9574V53ZM97.4166 54.72H92.9566V53H103.757V54.72H99.2966V67H97.4166V54.72ZM105.758 53H108.558L112.298 61.24H112.338L116.078 53H118.758V67H116.878V55.2H116.838L113.258 63.1H111.258L107.678 55.2H107.638V67H105.758V53ZM121.95 53H123.83V65.28H130.25V67H121.95V53Z" fill="#AEC1BF"/>
</svg>`,
			css: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M185.059 2.34315C183.559 0.842857 181.524 0 179.402 0H5C2.23858 0 0 2.23858 0 5V115C0 117.761 2.23858 120 5 120H204C206.761 120 209 117.761 209 115V29.5979C209 27.4762 208.157 25.4414 206.657 23.9411L185.059 2.34315Z" fill="#FFCACA"/>
</svg>`,
			scss: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
\t\t\t\t\t\t\t\t\t\t<path fill-rule="evenodd" clip-rule="evenodd" d="M4.43446 55.6798C1.93665 57.0924 0.687749 57.7987 0.271913 58.7271C-0.0906377 59.5365 -0.0906378 60.4635 0.271913 61.2729C0.68775 62.2013 1.93665 62.9076 4.43445 64.3202L99.6761 118.183C101.436 119.178 102.316 119.676 103.248 119.871C104.074 120.043 104.926 120.043 105.751 119.871C106.684 119.676 107.564 119.178 109.324 118.183L204.566 64.3202C207.063 62.9076 208.312 62.2013 208.728 61.2729C209.091 60.4635 209.091 59.5365 208.728 58.7271C208.312 57.7987 207.063 57.0924 204.566 55.6798L109.324 1.81716C107.564 0.821989 106.684 0.324405 105.751 0.129419C104.926 -0.0431398 104.074 -0.0431398 103.248 0.129419C102.316 0.324405 101.436 0.821989 99.6761 1.81716L4.43446 55.6798Z" fill="#FFC2E1"/>
\t\t\t\t\t\t\t\t\t</svg>`,
			bootstrap: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
\t\t\t\t\t\t\t\t\t\t<path fill-rule="evenodd" clip-rule="evenodd" d="M33.2781 0H75H134H135H175.722C188.636 0 191.616 7.10454 191.616 20.1639C192.411 48.0984 203.536 55.4098 209 55.5738V60V64.4262C203.536 64.5902 192.411 71.9016 191.616 99.8361C191.616 112.895 188.636 120 175.722 120H135H134H75H33.2781C20.3642 120 17.3841 112.895 17.3841 99.8361C16.5894 71.9016 5.46358 64.5902 0 64.4262V60V55.5738C5.46358 55.4098 16.5894 48.0984 17.3841 20.1639C17.3841 7.10454 20.3642 0 33.2781 0Z" fill="#CFB9FF"/>
\t\t\t\t\t\t\t\t\t</svg>`,
			js: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M0.793117 8.72428C0.51803 5.69833 0.380487 4.18536 0.885141 3.01715C1.32848 1.99088 2.10297 1.14278 3.0849 0.608346C4.20262 0 5.72183 0 8.76026 0H200.24C203.278 0 204.797 0 205.915 0.608346C206.897 1.14278 207.672 1.99088 208.115 3.01715C208.62 4.18536 208.482 5.69833 208.207 8.72429L199.595 103.46C199.383 105.789 199.277 106.954 198.773 107.87C198.328 108.678 197.669 109.348 196.867 109.804C195.958 110.322 194.795 110.445 192.469 110.691L105.342 119.911C105.027 119.944 104.869 119.961 104.711 119.968C104.57 119.974 104.43 119.974 104.289 119.968C104.131 119.961 103.973 119.944 103.658 119.911L16.5307 110.691C14.2046 110.445 13.0416 110.322 12.1328 109.804C11.3315 109.348 10.672 108.678 10.2273 107.87C9.72309 106.954 9.6172 105.789 9.40544 103.46L0.793117 8.72428Z" fill="#FFF6AD"/>
</svg>`,
			jquery: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
\t\t\t\t\t\t\t\t\t\t<path d="M18.7949 6.6909C19.1892 4.31397 19.3863 3.1255 19.9788 2.23358C20.501 1.44736 21.2351 0.825012 22.0961 0.438491C23.073 0 24.2777 0 26.6871 0H182.313C184.722 0 185.927 0 186.904 0.438491C187.765 0.825012 188.499 1.44736 189.021 2.23358C189.614 3.1255 189.811 4.31397 190.205 6.6909L207.456 110.691C207.987 113.894 208.253 115.495 207.788 116.743C207.381 117.839 206.603 118.757 205.589 119.338C204.434 120 202.811 120 199.564 120H9.4363C6.1895 120 4.5661 120 3.41089 119.338C2.39713 118.757 1.61896 117.839 1.2115 116.743C0.747183 115.495 1.01283 113.894 1.54413 110.691L18.7949 6.6909Z" fill="#C9E7FF"/>
\t\t\t\t\t\t\t\t\t</svg>`,
			pug: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M0 104.5C0 46.7862 46.7862 0 104.5 0C162.214 0 209 46.7862 209 104.5V114.545C209 114.968 209 115.179 208.987 115.357C208.81 117.837 206.837 119.81 204.357 119.987C204.179 120 203.968 120 203.545 120H5.45455C5.03247 120 4.82142 120 4.6433 119.987C2.1631 119.81 0.190127 117.837 0.0127394 115.357C0 115.179 0 114.968 0 114.545V104.5Z" fill="#EFCCA3"/>
</svg>`,
			vue: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M104.5 0H3.1126C0.447032 0 -0.9807 3.08265 0.769841 5.0583L101.376 118.603C103.027 120.466 105.973 120.466 107.624 118.603L208.23 5.0583C209.981 3.08265 208.553 0 205.887 0H104.5Z" fill="#97E6C3"/>
</svg>`,
			react: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M103.991 96.6932C71.5529 117.801 41.9286 126.124 33.3735 115.172C28.4482 108.869 31.409 97.3358 40.2126 83.6531C15.7356 78.1624 0 69.6088 0 60C0 50.3912 15.7357 41.8375 40.2128 36.3469C31.4091 22.664 28.4481 11.131 33.3733 4.82711C41.9289 -6.1236 71.553 2.19876 103.991 23.3066C136.429 2.19876 166.054 -6.1236 174.609 4.82711C179.511 11.1006 176.602 22.553 167.896 36.1493C192.882 41.6311 209 50.2752 209 60C209 69.7248 192.882 78.3689 167.897 83.8507C176.602 97.4468 179.51 108.899 174.609 115.172C166.054 126.124 136.43 117.801 103.991 96.6932Z" fill="#39D2FB"/>
</svg>`,
			ts: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M18.1529 2.49361C19.3148 0.925086 21.1512 0 23.1032 0H185.897C187.849 0 189.685 0.925085 190.847 2.49361C202.636 18.409 209 37.6912 209 57.4974V60V62.5026C209 82.3088 202.636 101.591 190.847 117.506C189.685 119.075 187.849 120 185.897 120H23.1032C21.1512 120 19.3148 119.075 18.1529 117.506C6.36368 101.591 0 82.3088 0 62.5026V60V57.4974C0 37.6912 6.36368 18.409 18.1529 2.49361Z" fill="#A2DAFF"/>
</svg>`,
			tilda: `<svg width="209" height="120" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
<path fill-rule="evenodd" clip-rule="evenodd" d="M60 115C60 117.761 62.2386 120 65 120H143C145.761 120 148 117.761 148 115V67H204C206.761 67 209 64.7614 209 62V5C209 2.23858 206.761 3.62805e-06 204 3.62805e-06H143.006C143.004 1.20949e-06 143.002 0 143 0L65 3.62805e-06H5C2.23858 3.62805e-06 0 2.23858 0 5V62C0 64.7614 2.23858 67 5 67H60V115Z" fill="#AEC1BF"/>
</svg>`,
			desktop: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
\t\t\t\t\t\t\t\t\t\t<path d="M0 24C0 15.5992 0 11.3988 1.6349 8.19014C3.073 5.36771 5.36771 3.073 8.19014 1.6349C11.3988 0 15.5992 0 24 0H185C193.401 0 197.601 0 200.81 1.6349C203.632 3.073 205.927 5.36771 207.365 8.19014C209 11.3988 209 15.5992 209 24V112C209 114.8 209 116.2 208.455 117.27C207.976 118.211 207.211 118.976 206.27 119.455C205.2 120 203.8 120 201 120H8C5.19974 120 3.79961 120 2.73005 119.455C1.78924 118.976 1.02433 118.211 0.544967 117.27C0 116.2 0 114.8 0 112V24Z" fill="#EADDD0"/>
\t\t\t\t\t\t\t\t\t</svg>`,
			mobile: `<svg width="100%" height="100%" viewBox="0 0 209 120" fill="none" xmlns="http://www.w3.org/2000/svg">
\t\t\t\t\t\t\t\t\t\t<path fill-rule="evenodd" clip-rule="evenodd" d="M2.72484 13.6502C0 18.998 0 25.9987 0 40V80C0 94.0013 0 101.002 2.72484 106.35C5.12167 111.054 8.94619 114.878 13.6502 117.275C18.998 120 25.9987 120 40 120H169C183.001 120 190.002 120 195.35 117.275C200.054 114.878 203.878 111.054 206.275 106.35C209 101.002 209 94.0013 209 80V40C209 25.9987 209 18.998 206.275 13.6502C203.878 8.94619 200.054 5.12167 195.35 2.72484C190.002 0 183.001 0 169 0H40C25.9987 0 18.998 0 13.6502 2.72484C8.94619 5.12167 5.12167 8.94619 2.72484 13.6502ZM198 63C199.657 63 201 61.6569 201 60C201 58.3431 199.657 57 198 57C196.343 57 195 58.3431 195 60C195 61.6569 196.343 63 198 63Z" fill="#D7FFDD"/>
\t\t\t\t\t\t\t\t\t</svg>`,



			right: [
				{
					title: "1С-Просто",
					description: "Сайт для бабла",
					date: "2021—2022",
					technologies: [
						{
							svg: this.html,
							name: 'HTML'
						},
						{
							svg: this.scss,
							name: 'CSS'
						},
						{
							svg: this.jquery,
							name: 'JQuery'
						},
						{
							svg: this.bootstrap,
							name: 'Bootstrap'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
						{
							svg: this.mobile,
							name: 'Mobile'
						},
					]
				},
				{
					title: "Ilona Lunden",
					description: "Сайт для бабла",
					date: "2021—2022",
					technologies: [
						{
							svg: this.vue,
							name: 'Vue'
						},
						{
							svg: this.pug,
							name: 'Pug'
						},
						{
							svg: this.scss,
							name: 'SCSS'
						},
						{
							svg: this.jquery,
							name: 'JQuery'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
						{
							svg: this.mobile,
							name: 'Mobile'
						},
					]
				},
				{
					title: "No One",
					description: "Сайт для бабла",
					date: "2021—2022",
					technologies: [
						{
							svg: this.pug,
							name: 'Pug'
						},
						{
							svg: this.scss,
							name: 'SCSS'
						},
						{
							svg: this.jquery,
							name: 'JQuery'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
						{
							svg: this.mobile,
							name: 'Mobile'
						},
					]
				},
				{
					title: "Студия дизайна Алексея Сушкова",
					description: "Сайт для бабла",
					date: "2021—2022",
					technologies: [
						{
							svg: this.html,
							name: 'HTML'
						},
						{
							svg: this.css,
							name: 'CSS'
						},
					]
				},
				{
					title: 'EAC',
					description: 'Сайт для бабла',
					date: '2021',
					technologies: [
						{
							svg: this.react,
							name: 'React'
						},
						{
							svg: this.ts,
							name: 'TypeScript'
						},
						{
							svg: this.desktop,
							name: 'Desktop'
						},
					]
				},
				{
					title: 'Omni rating',
					description: 'Сайт для бабла',
					date: '2021',
					technologies: [
						{
							svg: this.tilda,
							name: 'Tilda'
						},
					]
				},
			],

		};
	},

	methods: {
		clickOutside() {
			console.log('left.popover', this.popover);
			this.popover = false;
		},
		clickInside() {
			console.log('click right');
		},
		add() {
			this.popover = true;
			console.log('add', this.html);

			// if (this.popover) {
			// 	this.html = this.htmlStroke;
			//
			// 	console.log('html', this.html);
			// }
		},
		close() {
			this.popover = false;
			this.over = false;
			console.log('close', this.popover);
		},
		mouseOver() {
			console.log('мыш кродётся');
			this.over = true;
		},
		mouseLeave() {
			console.log('мыш убежала');
			this.over = false;
		}

	},



	mounted() {
		console.log('this.popover', this.popover === true);
		if (this.popover) {
			this.html = this.htmlStroke;

			console.log('html', this.html);
		}
		console.log(this.html);
		// const left = [
		// 	{
		// 		title: 'Сайт Ярослава Туголуковского',
		// 		description: 'Сайт для души',
		// 		date: '2021-2022',
		// 		technologies: [
		// 			{
		// 				svg: this.html,
		// 				name: 'HTML'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'CSS'
		// 			},
		// 			{
		// 				svg: this.jquery,
		// 				name: 'JQuery'
		// 			},
		// 			{
		// 				svg: this.bootstrap,
		// 				name: 'Bootstrap'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 			{
		// 				svg: this.mobile,
		// 				name: 'Mobile'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: 'Колорлон',
		// 		description: 'Сайт для бабла',
		// 		date: '2021',
		// 		technologies: [
		// 			{
		// 				svg: this.pug,
		// 				name: 'Pug'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'SCSS'
		// 			},
		// 			{
		// 				svg: this.js,
		// 				name: 'JavaScript'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: 'Acer',
		// 		description: 'Сайт для бабла',
		// 		date: '2021',
		// 		technologies: [
		// 			{
		// 				svg: this.pug,
		// 				name: 'Pug'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'SCSS'
		// 			},
		// 			{
		// 				svg: this.js,
		// 				name: 'JavaScript'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 			{
		// 				svg: this.mobile,
		// 				name: 'Mobile'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: 'Madeleine',
		// 		description: 'Сайт для бабла',
		// 		date: '2021',
		// 		technologies: [
		// 			{
		// 				svg: this.pug,
		// 				name: 'Pug'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'SCSS'
		// 			},
		// 			{
		// 				svg: this.jquery,
		// 				name: 'JQuery'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 			{
		// 				svg: this.mobile,
		// 				name: 'Mobile'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: 'Fonar.tv',
		// 		description: 'Сайт для бабла',
		// 		date: '2020-2022',
		// 		technologies: [
		// 			{
		// 				svg: this.html,
		// 				name: 'HTML'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'SCSS'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 			{
		// 				svg: this.mobile,
		// 				name: 'Mobile'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: 'CRM Sijeko',
		// 		description: 'Сайт для бабла',
		// 		date: '2020',
		// 		technologies: [
		// 			{
		// 				svg: this.vue,
		// 				name: 'Vue'
		// 			},
		// 		]
		// 	},
		// ];


		// this.left.forEach(element => this.leftProjects.push(element));

		// const right = [
		// 	{
		// 		title: "1С-Просто",
		// 		description: "Сайт для бабла",
		// 		date: "2021—2022",
		// 		technologies: [
		// 			{
		// 				svg: this.html,
		// 				name: 'HTML'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'CSS'
		// 			},
		// 			{
		// 				svg: this.jquery,
		// 				name: 'JQuery'
		// 			},
		// 			{
		// 				svg: this.bootstrap,
		// 				name: 'Bootstrap'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 			{
		// 				svg: this.mobile,
		// 				name: 'Mobile'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: "Ilona Lunden",
		// 		description: "Сайт для бабла",
		// 		date: "2021—2022",
		// 		technologies: [
		// 			{
		// 				svg: this.vue,
		// 				name: 'Vue'
		// 			},
		// 			{
		// 				svg: this.pug,
		// 				name: 'Pug'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'SCSS'
		// 			},
		// 			{
		// 				svg: this.jquery,
		// 				name: 'JQuery'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 			{
		// 				svg: this.mobile,
		// 				name: 'Mobile'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: "No One",
		// 		description: "Сайт для бабла",
		// 		date: "2021—2022",
		// 		technologies: [
		// 			{
		// 				svg: this.pug,
		// 				name: 'Pug'
		// 			},
		// 			{
		// 				svg: this.scss,
		// 				name: 'SCSS'
		// 			},
		// 			{
		// 				svg: this.jquery,
		// 				name: 'JQuery'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 			{
		// 				svg: this.mobile,
		// 				name: 'Mobile'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: "Студия дизайна Алексея Сушкова",
		// 		description: "Сайт для бабла",
		// 		date: "2021—2022",
		// 		technologies: [
		// 			{
		// 				svg: this.html,
		// 				name: 'HTML'
		// 			},
		// 			{
		// 				svg: this.css,
		// 				name: 'CSS'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: 'EAC',
		// 		description: 'Сайт для бабла',
		// 		date: '2021',
		// 		technologies: [
		// 			{
		// 				svg: this.react,
		// 				name: 'React'
		// 			},
		// 			{
		// 				svg: this.ts,
		// 				name: 'TypeScript'
		// 			},
		// 			{
		// 				svg: this.desktop,
		// 				name: 'Desktop'
		// 			},
		// 		]
		// 	},
		// 	{
		// 		title: 'Omni rating',
		// 		description: 'Сайт для бабла',
		// 		date: '2021',
		// 		technologies: [
		// 			{
		// 				svg: this.tilda,
		// 				name: 'Tilda'
		// 			},
		// 		]
		// 	},
		// ];

		// this.right.forEach(element => this.rightProjects.push(element));
	}
};

</script>

<style lang="scss">
@import "assets/scss/style";
</style>
