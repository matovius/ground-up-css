<script lang="ts">
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import Form from '$lib/components/Form.svelte';
</script>

<svelte:head>
	<title>Ground Up CSS</title>
</svelte:head>

<Header />

<!-- HOME PAGE -->
<main class="main">
	<section id="hero" class="hero-section">
		<div class="container container-1200">
			<div class="headline">
				<h1 class="h1 heading">
					THE COMPREHENSIVE NEWSLETTER<br />
					FOR THE
					<span class="dark-text">CSS LOVER</span>
				</h1>
				<h2 class="h4 subheading">With a new issue out every Saturday</h2>
			</div>

			<div class="hero-form">
				<Form emailLabel="Enter your email address" ctaText="Join" />
			</div>
		</div>
	</section>

	<section id="incentives" class="incentives-section">
		<div class="container container-1200">
			<div class="incentive">
				<h2 class="h2 heading">
					The incredible genius<br />Albert Einstein once said:
				</h2>
				<blockquote class="quote-wrapper">
					<span class="bg-quote-motif">"</span>
					<p class="h3 quote">
						CSS is the eleventh wonder of the world.<br />
						The one who understands it, makes it do their bidding.<br />
						The one who doesn't, calls it magic.
					</p>
					<cite>Albert Einstein, probably</cite>
				</blockquote>
			</div>

			<div class="incentive">
				<h2 class="h2 heading">
					And astronomer and OG CSS artist<br />Galileo Galilei also once stated:
				</h2>
				<blockquote class="quote-wrapper">
					<span class="bg-quote-motif">"</span>
					<p class="h3 quote">
						To understand the frontend, you must understand<br />
						the languages in which it's written, one of which is CSS.
					</p>
					<cite>Galileo Galilei, probably</cite>
				</blockquote>
			</div>

			<div class="final-cta">
				<h2 class="h1 heading">So what are you waiting for?</h2>
				<h3 class="h2 subheading">Join the mailing list and upgrade your CSS game.</h3>

				<div class="final-form">
					<Form emailLabel="Enter your email address" ctaText="Join" />
				</div>
			</div>
		</div>
	</section>
</main>

<Footer />

<style>
	.main {
		width: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.hero-section,
	.incentives-section {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 60px 20px;

		& > .container {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 40px;
		}
	}

	.hero-section {
		& .headline {
			font-family: var(--font-anton);
			text-align: center;
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 20px;
			color: hsl(var(--clr-ghost-white));

			& .dark-text {
				color: hsl(var(--clr-russian-violet));
			}

			& > .subheading {
				color: hsl(var(--clr-imperial-red));
			}
		}

		& .hero-form {
			width: 100%;
			display: flex;
			justify-content: center;
			align-items: center;
		}
	}

	.incentives-section {
		& > .container {
			gap: 80px;
		}
		& .incentive {
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 20px;

			& > .heading {
				font-family: var(--font-anton);
				text-align: center;
			}

			& .quote-wrapper {
				width: 100%;
				max-width: 900px;
				padding: 20px;
				border-radius: 20px;
				background: hsl(var(--clr-russian-violet));
				position: relative;
				isolation: isolate;

				@media screen and (min-width: 600px) {
					padding: 40px;
				}

				& > .bg-quote-motif {
					color: hsl(var(--clr-ghost-white));
					font-family: var(--font-anton);
					font-size: 140px;
					position: absolute;
					top: 0;
					left: 0;
					line-height: 0.5;
					z-index: 5;
					user-select: none;
					-moz-user-select: none;
					-webkit-user-select: none;
					pointer-events: none;
				}

				& > .quote {
					font-family: var(--font-anton);
					line-height: 1.2;
					padding-bottom: 20px;
				}

				& > cite {
					color: hsl(var(--clr-ghost-white), 0.6);
				}
			}
		}

		& .final-cta {
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 20px;

			& > .heading {
				font-family: var(--font-anton);
				text-align: center;
				width: 100%;
			}
			& > .subheading {
				font-family: var(--font-anton);
				text-align: center;
				color: hsl(var(--clr-russian-violet));
				width: 100%;
			}

			& > .final-form {
				width: 100%;
				display: flex;
				justify-content: center;
				align-items: center;
				padding-top: 20px;
			}
		}
	}
</style>
