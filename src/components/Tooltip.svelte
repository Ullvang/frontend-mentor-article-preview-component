<script>
	import facebook from '$lib/assets/images/svgs/icon-facebook.svg';
	import twitter from '$lib/assets/images/svgs/icon-twitter.svg';
	import pinterest from '$lib/assets/images/svgs/icon-pinterest.svg';
</script>

<div id="tooltip" on:mouseenter on:mouseleave>
	<p>Share</p>
	<div id="logos">
		<img src={facebook} alt="facebook logo" />
		<img src={twitter} alt="twitter logo" />
		<img src={pinterest} alt="pinterest logo" />
	</div>
</div>

<style>
	#tooltip {
		position: absolute;
		background-color: var(--very-dark-grayish-blue);
		color: var(--grayish-blue);
		padding: 18px 36px 17px 37px;
		top: -83px;
		left: -114px;
		border-radius: 10px;
		display: flex;
	}
	#tooltip:after {
		content: '';
		position: absolute;
		left: 118px;
		bottom: -12px;
		width: 24;
		height: 12;
		border-left: 12px solid transparent;
		border-right: 12px solid transparent;
		border-top: 12px solid var(--very-dark-grayish-blue);

		clear: both;
	}
	#logos {
		margin-left: 21px;
		display: flex;
		gap: 16px;
	}
	p {
		width: 62px;
		font-size: 13px;
		letter-spacing: 5px;
		line-height: 20px;
		text-transform: uppercase;
	}
	@media only screen and (max-width: 820px) {
		#tooltip {
			left: -190px;
		}
		#tooltip:after {
			left: 194px;
		}
	}
</style>
