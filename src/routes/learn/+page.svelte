<script lang="ts">
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>Learn - Ground Up CSS</title>
</svelte:head>

<Header />

<!-- LEARN PAGE -->
<main class="main">
	<section id="hero" class="hero-section">
		<div class="container container-1200">
			<div class="headline">
				<h1 class="h1 heading">LEARN MORE ABOUT CSS</h1>
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
	.directive-section,
	.features-section {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 120px 15px;

		@media screen and (min-width: 600px) {
			padding: 120px 60px;
		}

		@media screen and (min-width: 1200px) {
			padding: 120px;
		}

		& > .container {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
		}
	}

	.hero-section {
		background: hsl(var(--clr-russian-violet));

		& .headline {
			text-align: center;
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			color: hsl(var(--clr-ghost-white));
		}
	}

	.directive-section {
		& > .container {
			justify-content: start;
			align-items: start;
			flex-direction: row;
			flex-wrap: wrap;
			gap: 20px;
		}
	}

	.features-section {
		padding-top: 0;
		padding-bottom: 120px;

		& > .container {
			gap: 120px;
		}

		& .heading {
			text-align: center;
			text-shadow: 0 10px 0 hsl(var(--clr-black), 0.2);
			font-family: var(--font-anton);
			font-size: 48px;
			max-width: 30ch;

			@media screen and (min-width: 600px) {
				font-size: 60px;
			}

			@media screen and (min-width: 1200px) {
				font-size: 5vw;
			}
		}

		& .quote-wrapper {
			width: 100%;
			padding: 40px;
			border-radius: 20px;
			background: hsl(var(--clr-russian-violet));
			box-shadow: var(--shadow-10) hsl(var(--clr-black), 0.4);

			& > .quote {
				font-family: var(--font-anton);
				line-height: 1.2;
				padding-bottom: 20px;
			}
		}
	}

	.card {
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: 40px;
		padding: 40px;
		border-radius: 20px;
		border: 2px solid hsl(var(--clr-russian-violet));

		& > .headline {
			display: flex;
			flex-direction: column-reverse;
			gap: 20px;

			& > .heading,
			.subheading {
				font-family: var(--font-anton);
			}

			& > .subheading {
				text-transform: uppercase;
				color: hsl(var(--clr-russian-violet));
			}
		}

		& > .description {
			color: hsl(var(--clr-russian-violet));
		}

		& > .cta {
			width: 100%;
			display: flex;
			justify-content: flex-end;
			align-items: flex-end;
		}
	}

	.start-here,
	.coming-soon {
		width: 100%;

		@media screen and (min-width: 800px) {
			max-width: calc(50% - 10px);
		}
	}

	.coming-soon {
		@media screen and (min-width: 1200px) {
			height: 100%;
		}

		& > .cta {
			opacity: 0.5;
		}
	}

	@keyframes relief-settle {
		0% {
			scale: 0.8;
			text-shadow: 0 0 0 hsl(var(--clr-black), 1);
		}
		10% {
			scale: 0.9;
			text-shadow: 0 1px 0 hsl(var(--clr-black), 0.8);
		}
		20% {
			scale: 1;
			text-shadow: 0 2px 0 hsl(var(--clr-black), 0.7);
		}
		50% {
			scale: 1.1;
			text-shadow: 0 4px 0 hsl(var(--clr-black), 0.6);
		}
		60% {
			scale: 1.2;
			text-shadow: 0 6px 0 hsl(var(--clr-black), 0.5);
		}
		100% {
			scale: 1;
			text-shadow: 0 5px 0 hsl(var(--clr-black), 0.2);
		}
	}
</style>
