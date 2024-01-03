<script lang="ts">
	import { SiteLinks } from '$lib';
</script>

<footer class="footer">
	<div class="container container-1200">
		<div class="made-by-matovius">
			<span class="p statement">
				Made by
				<a
					href="https://matovius.pages.dev"
					target="_blank"
					rel="noopener noreferrer"
					class="self-link"
				>
					<svg class="icon" viewBox="0 0 500 500" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path
							d="M358.823 154.289L486.702 282.075C515.11 310.462 494.99 359 454.815 359H45.0945C20.1895 359 -0.00012207 338.825 -0.00012207 313.938V186.152C-0.00012207 146.006 48.5732 125.901 76.9812 154.289L204.86 282.075C233.268 310.462 281.842 290.357 281.842 250.211V186.152C281.842 146.006 330.415 125.901 358.823 154.289Z"
							fill="currentColor"
						/>
					</svg>
				</a>
			</span>
		</div>
	</div>
</footer>

<style>
	.footer {
		width: 100%;
		display: flex;
		justify-content: center;
		align-items: center;
		background: hsl(var(--clr-russian-violet));

		& .button {
			color: hsl(var(--clr-ghost-white));
			background: hsl(var(--clr-russian-violet));

			& > .front {
				border: 2px solid hsl(var(--clr-russian-violet));
				background: hsl(var(--clr-imperial-red));
			}
		}

		& > .container {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 40px;
			padding: 40px;
		}
	}

	.made-by-matovius {
		color: hsl(var(--clr-ghost-white), 0.6);

		& > .statement {
			display: flex;
			flex-direction: row;
			justify-content: center;
			align-items: center;
			gap: 10px;
		}

		& .self-link {
			display: inline-block;
			width: 30px;
			height: 30px;
			aspect-ratio: 1;
			color: inherit;
			text-decoration: none;
			outline: 2px solid transparent;
			outline-offset: 4px;

			&:hover {
				color: hsl(var(--clr-ghost-white));
			}

			&:focus-visible {
				outline-color: hsl(var(--clr-ghost-white));
			}

			&:visited {
				color: inherit;
			}
		}
	}
</style>
