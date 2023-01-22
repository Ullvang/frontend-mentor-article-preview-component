<slot />

<style global>
	:root {
		--very-dark-grayish-blue: hsl(217, 19%, 35%); /*#48556A*/
		--desaturated-dark-blue: hsl(214, 17%, 51%); /* #6E8098 */
		--grayish-blue: hsl(212, 23%, 69%); /* #9DAEC2 */
		--light-grayish-blue: hsl(210, 46%, 95%); /* #ECF2F8 */
	}
	:global(body) {
		margin: 0px;
		display: grid;
		grid-template-rows: 1fr auto 1fr;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		min-height: 100vh;
		background-color: var(--light-grayish-blue);
	}
	:global(*) {
		font-family: 'Manrope', sans-serif;
		font-weight: 500;
		margin: 0px;
	}
	:global(p) {
		font-size: 13px;
		letter-spacing: 0.12px;
		line-height: 20px;
	}
</style>
