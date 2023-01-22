<script lang="ts">
	import drawers from '$lib/assets/images/drawers.jpg';
	import avatarMichelle from '$lib/assets/images/avatar-michelle.jpg';
	import IconShare from '$lib/assets/images/svgs/svg-components/IconShare.svelte';
	import Footer from '../components/Footer.svelte';
	import Tooltip from '../components/Tooltip.svelte';

	let fill = '#6E8098';
	let showTooltip = false;
	let timeout: string | number | undefined | ReturnType<typeof setTimeout> = undefined;
</script>

<main>
	<img src={drawers} alt="drawers" />
	<article>
		<h1>
			Shift the overall look and feel by adding these wonderful touches to furniture in your home
		</h1>
		<p id="text-content">
			Ever been in a room and felt like something was missing? Perhaps it felt slightly bare and
			uninviting. I’ve got some simple tips to help you make any room feel complete.
		</p>
		<div id="card-footer">
			<div id="left-side-card-footer">
				<img id="avatar" src={avatarMichelle} alt="avatar michelle appleton" />
				<div>
					<p id="name">Michelle Appleton</p>
					<p id="date">28 Jun 2020</p>
				</div>
			</div>
			<div style="position: relative;">
				<div
					id="share-button-container"
					on:mouseenter={() => {
						fill = '#fff';
						showTooltip = true;
					}}
					on:mouseleave={() => {
						fill = '#6E8098';
						timeout = setTimeout(() => {
							showTooltip = false;
						}, 200);
					}}
				>
					<IconShare {fill} />
				</div>
				{#if showTooltip}
					<Tooltip
						on:mouseenter={() => {
							clearTimeout(timeout);
							showTooltip = true;
						}}
						on:mouseleave={() => {
							showTooltip = false;
						}}
					/>
				{/if}
			</div>
		</div>
	</article>
</main>

<Footer />

<style>
	h1 {
		font-size: 20px;
		color: var(--very-dark-grayish-blue);
		font-weight: bold;
		line-height: 28px;
		letter-spacing: 0.25px;
	}
	main {
		display: flex;
		grid-row-start: 2;
		max-width: 730px;
		min-height: 280px;
		border-radius: 10px;
	}
	article {
		background-color: #fff;
		padding: 32px 40px;
		border-radius: 0px 10px 10px 0px;
	}
	img {
		width: 285px;
		height: 280px;
		object-fit: cover;
		object-position: 0px;
		border-radius: 10px 0px 0px 10px;
	}

	#text-content {
		margin: 12px 0px 20px;
		color: var(--desaturated-dark-blue);
		letter-spacing: 0.12px;
		line-height: 20px;
	}
	#card-footer {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	#left-side-card-footer {
		display: flex;
	}
	#avatar {
		width: 40px;
		height: 40px;
		border-radius: 50%;
		margin-right: 16px;
	}
	#date {
		color: var(--grayish-blue);
	}
	#share-button-container {
		display: flex;
		justify-content: center;
		align-items: center;
		border-radius: 50%;
		background-color: var(--light-grayish-blue);
		width: 32px;
		height: 32px;
	}
	#share-button-container:hover {
		background-color: var(--desaturated-dark-blue);
	}

	#name {
		font-weight: bold;
	}

	@media only screen and (max-width: 820px) {
		:global(body) {
			grid-template-rows: auto 1fr;
			padding-top: 74px;
			box-sizing: border-box;
		}
		main {
			flex-direction: column;
			max-width: 327px;
			margin: 0px 24px;
			margin-bottom: auto;
		}
		article {
			padding: 36px 32px;
		}
		img {
			width: 100%;
		}
		h1 {
			font-size: 16px;
			letter-spacing: 0.2px;
			line-height: 24px;
		}
	}
</style>
