<template>
	<header class="header emerge">
		<div class="container">
			<div class="row">
				<div class="col-sm-12 col-md-12 col-lg-12 col-xl-12">
					<div class="header__blocks">
						<div class="header__title">
							<div class="header__title-name">
								<div class="header__title-ava emerge" data-effect="relax" data-duration="300" data-continue="true">
								</div>
							</div>
						</div>

						<div class="header__links">
							<a class="link-active" href="https://www.instagram.com/tugolukovskiy/" target="_blank">инстаграм</a>
						</div>
					</div>
				</div>
			</div>
			<div class="row">
				<div class="col-sm-12 col-md-12 col-lg-12 col-xl-12">
					<div class="header__desc">

					</div>
				</div>
			</div>
		</div>
	</header>

	<main>
		<section class="row-1">
			<div class="container">
				<div class="row">
					<div class="col-sm-12 col-md-7 col-lg-7 col-xl-7">
						<div class="video emerge" data-effect="slide" data-duration="300" data-down="20px" data-right="25%" data-continue="true">
						</div>
					</div>

					<div
						class="col-sm-12 offset-sm-0 col-md-3 offset-md-1 col-lg-3 offset-lg-1 col-xl-3 offset-xl-1">
						<div class="travel emerge" data-effect="slide" data-duration="300" data-bottom="20px" data-left="25%" data-continue="true">
							<div class="travel__link">
							</div>
						</div>
					</div>
				</div>
			</div>
		</section>
	</main>

	<footer class="footer">
		<div class="container">
			<div class="row">
				<div class="col-12">
					<div class="page-info">
						<div class="col-12 col-md-6">
						</div>
					</div>
				</div>
			</div>
			<div class="row">
				<div class="col-xl-12">
					<div class="footer__blocks">
						<div class="footer__year">
							<p>&#169; 2013 <span class="footer__dash">———</span>
								<span class="footer__dash-mob">—————————————————————</span> 2022</p>
						</div>

						<div class="footer__dev">
							<span>Сайт собран </span><a class="link-active" href="https://t.me/kostennikov" target="_blank">
							Пашей Костенниковым</a>
						</div>

						<div class="footer__links">
						</div>
					</div>
				</div>
			</div>
		</div>

	</footer>
</template>

<style lang="scss">

@import "./assets/mixins";
@import "./assets/custom";
@import "~bootstrap/scss/bootstrap";


body {
	padding: 0;
	margin: 0;
}
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	background-color: #869E9B;
	font-size: calc(0.723vw + 0.0073px);
	height: 100vh;

	@media (min-width: 1920px) {
		font-size: 14px;
	}
}
</style>
