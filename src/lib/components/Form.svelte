<script lang="ts">
	export let emailPlaceholder: string = 'email@example.com';
	export let emailLabel: string = 'Email address';
	export let ctaText: string = 'Join the newsletter';
</script>

<form class="form">
	<label for="email-input" class="input-label">
		<span class="p label-text email-label">{emailLabel}</span>
		<input
			type="email"
			name="email"
			id="email-input"
			class="input email-input"
			placeholder={emailPlaceholder}
			required
		/>
	</label>
	<div class="cta">
		<button type="button" class="button submit-button">
			<div class="front">
				<span>{ctaText}</span>
			</div>
		</button>
	</div>
</form>

<style>
	.form {
		width: 100%;
		max-width: 600px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 20px;

		& > .input-label {
			color: hsl(var(--clr-russian-violet));
			width: 100%;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 5px;

			& > .input {
				text-align: center;
				width: 100%;
				padding: 10px 20px;
				border-radius: 9999rem;
				border: 2px solid hsl(var(--clr-russian-violet));
				background: transparent;
				outline: 2px solid transparent;
				outline-offset: 4px;

				&::placeholder {
					color: hsl(var(--clr-russian-violet), 0.6);
				}

				&:focus-visible {
					outline-color: hsl(var(--clr-brandeis-blue));
				}
			}
		}

		& > .cta {
			width: 100%;
			display: flex;
			justify-content: center;
			align-items: center;
		}

		& .button {
			width: 100%;
			color: hsl(var(--clr-ghost-white));
			background: hsl(var(--clr-russian-violet));

			@media screen and (min-width: 400px) {
				width: fit-content;
			}

			& > .front {
				padding-left: 80px;
				padding-right: 80px;
				border: 2px solid hsl(var(--clr-russian-violet));
				background: hsl(var(--clr-imperial-red));
			}
		}
	}
</style>
