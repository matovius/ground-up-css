<script lang="ts">
	import { onMount } from 'svelte';
	import Logo from '$lib/components/Logo.svelte';
	import { SiteLinks } from '$lib';

	let Header: HTMLElement;

	let MenuDialog: HTMLDialogElement;
	let menuDialogOpen: boolean = false;

	let MenuDialogBackdrop: HTMLElement;
	let MenuDialogMenu: HTMLElement;

	function setScrolled() {
		if (window.scrollY > 5) {
			//console.log(window.scrollY);
			Header.style.borderColor = 'hsl(var(--clr-russian-violet))';
		} else {
			Header.style.removeProperty('border-color');
		}
	}

	function animateMenu() {
		MenuDialogBackdrop.style.transform = 'translateY(0)';
		setTimeout(() => {
			MenuDialogMenu.style.opacity = '1';
		}, 200);
	}

	function deAnimateMenu() {
		MenuDialogMenu.style.opacity = '0';
		setTimeout(() => {
			MenuDialogBackdrop.style.transform = 'translateY(-100%)';
		}, 200);
	}

	function toggleMenuDialog() {
		if (!menuDialogOpen) {
			document.body.style.overflow = 'hidden';
			MenuDialog.showModal();
			setTimeout(animateMenu, 10);
			menuDialogOpen = true;
		} else {
			deAnimateMenu();
			setTimeout(() => {
				MenuDialog.close();
			}, 500);
			document.body.style.overflow = 'auto';
			menuDialogOpen = false;
		}
	}

	onMount(() => {
		window.onscroll = () => {
			setScrolled();
		};

		// MenuDialog.showModal();
	});
</script>

<header class="header" bind:this={Header}>
	<div class="container">
		<div class="logo-wrapper">
			<Logo />
		</div>

		<div class="open-menu-wrapper">
			<button class="button three-d" on:click={toggleMenuDialog}>
				<div class="front">
					<span>Menu</span>
				</div>
			</button>
		</div>
	</div>
</header>

<dialog id="menu-dialog" class="dialog" bind:this={MenuDialog}>
	<div class="menu-wrapper">
		<div class="backdrop" bind:this={MenuDialogBackdrop}></div>

		<div class="menu" bind:this={MenuDialogMenu}>
			<header class="menu-header">
				<div class="container container-1200">
					<div class="logo-wrapper">
						<Logo />
					</div>

					<div class="close-menu-wrapper">
						<button class="button three-d close-button" on:click={toggleMenuDialog}>
							<div class="front">
								<span>Close</span>
							</div>
						</button>
					</div>
				</div>
			</header>
			<main class="menu-main">
				<nav class="container container-1200">
					<ul class="nav-list">
						{#each SiteLinks as Link}
							<li class="nav-item">
								<a href={Link.url} class="h1 nav-link">{Link.label}</a>
							</li>
						{/each}
					</ul>
					<div></div>
				</nav>
			</main>
		</div>
	</div>
</dialog>

<style>
	.header {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		background: hsl(var(--clr-jonquil));
		border-bottom: 2px solid transparent;
		position: sticky;
		top: 0;
		z-index: 9999;

		& .button {
			color: hsl(var(--clr-ghost-white));
			background: hsl(var(--clr-russian-violet));

			& > .front {
				border: 2px solid hsl(var(--clr-russian-violet));
				background: hsl(var(--clr-imperial-red));
			}
		}

		& > .container {
			width: 100%;
			max-width: 1200px;
			display: flex;
			flex-direction: row;
			justify-content: space-between;
			align-items: center;
			gap: 20px;
			padding: 20px;

			& > .logo-wrapper {
				width: 60px;
				height: 60px;
				aspect-ratio: 1;
			}
		}
	}

	.dialog {
		width: 0;
		height: 0;
		overflow: visible;
		position: relative;

		&::backdrop {
			background: transparent;
		}

		& .button {
			color: hsl(var(--clr-russian-violet));
			background: hsl(var(--clr-ghost-white));

			& > .front {
				border: 2px solid hsl(var(--clr-ghost-white));
				background: hsl(var(--clr-jonquil));
			}
		}
	}

	.menu-wrapper {
		isolation: isolate;
		overflow: hidden;
		position: fixed;
		top: 0;
		left: 0;
		width: 100dvw;
		height: 100dvh;
		background: transparent;

		& > .backdrop {
			width: 100%;
			height: 100%;
			background: hsl(var(--clr-russian-violet));
			z-index: -1;
			position: absolute;
			transform: translateY(-100%);
		}
	}

	.menu {
		width: 100%;
		height: 100%;
		overflow-y: auto;
		opacity: 0;

		& > .menu-header {
			width: 100%;
			display: flex;
			justify-content: center;
			align-items: center;

			& > .container {
				display: flex;
				flex-direction: row;
				justify-content: space-between;
				align-items: center;
				gap: 20px;
				padding: 20px;

				& > .logo-wrapper {
					width: 60px;
					height: 60px;
					aspect-ratio: 1;

					@media screen and (min-width: 600px) {
						width: 90px;
						height: 90px;
					}

					@media screen and (min-width: 1200px) {
						width: 120px;
						height: 120px;
					}
				}
			}
		}

		& > .menu-main {
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: start;
			align-items: center;

			& > .container {
				display: flex;
				flex-direction: column;
				justify-content: start;
				align-items: center;
				gap: 20px;
				padding: 20px;
			}
		}
	}

	.nav-list {
		color: hsl(var(--clr-ghost-white));
		list-style-type: none;
		display: flex;
		flex-direction: column;
		justify-content: start;
		align-items: center;
		gap: 20px;
		padding: 20px;

		@media screen and (min-width: 600px) {
			gap: 40px;
			padding: 40px;
		}

		& .nav-link {
			font-family: var(--font-anton);
			color: hsl(var(--clr-ghost-white), 0.6);
			text-decoration: none;
			outline: none;

			&:hover,
			&:focus-visible {
				color: hsl(var(--clr-ghost-white));
			}
		}
	}
</style>
