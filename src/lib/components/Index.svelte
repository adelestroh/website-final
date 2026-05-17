<script lang="ts">
	const anchor = `--a-${crypto.randomUUID()}`;
	import Cloudy from '$lib/assets/ui-elements/cloudy_icon.svg';

	let { time, src, children }: { time: string; src: string; children: any } = $props();
</script>

<button popovertarget={anchor} class="index-item" style:anchor-name={anchor}>
	<span class="date">{time}</span>
	<div class="index-content" id={anchor} style:position-anchor={anchor} popover>
		<div class="top-bar">
			<p>12°C</p>
			<img src={Cloudy} class="temp-icon" />
		</div>
		<div class="content"><img {src} alt="" /></div>
		<div class="content">{@render children()}</div>
	</div>
</button>

<style>
	.index-item {
		display: flex;
		justify-content: space-between;
		align-items: center;

		font-size: 20px;
		width: 100%;
		color: white;
		padding: 0 10px;
		height: 50px;
		flex-shrink: 0;
		text-align: unset;

		cursor: pointer;
		z-index: 2;

		text-shadow:
			0 0 10px rgba(155, 154, 154, 1),
			0 0 10px rgba(155, 154, 154, 1),
			0 0 10px rgba(155, 154, 154, 1);

		border: unset;
		background: unset;
		border-radius: 18px;
		box-shadow:
			0 0 10px rgba(235, 235, 235, 0.5),
			0 0 20px rgba(198, 198, 198, 0.25);

		&:has(> .index-content:popover-open) {
			background: rgba(171, 165, 153, 0.249);
		}
	}

	.index-content {
		box-sizing: border-box;
		margin: 0;
		padding: unset;
		position: absolute;
		inset: auto;
		top: calc(anchor(bottom) + 10px);
		right: anchor(right);
		border: unset;
		position-visibility: always;
		position-try-fallbacks: --above-right;

		width: calc(anchor-size(width) * 0.7);

		background: rgba(198, 198, 198, 0.66);
		border-radius: 16px;

		box-shadow:
			0 0 20px rgba(210, 210, 210, 0.8),
			0 0 40px rgba(198, 198, 198, 0.25);

		color: white;

		text-shadow: 0 0 10px rgba(155, 154, 154, 1);

		&:popover-open {
			display: grid;
			grid-template-columns: 300px 1fr;
			grid-template-rows: 50px minmax(0, 1fr);
		}
	}

	.content {
		width: 100%;
		height: 100%;
		padding: 10px;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;

		& > img {
			max-width: 100%;
			object-fit: contain;
			width: auto;
		}
	}

	.top-bar {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: flex-end;
		gap: 10px;
		grid-column: span 2;

		img {
			height: 100%;
			filter: drop-shadow(0 0 6px rgb(71, 71, 71));
		}
	}

	@position-try --above-right {
		inset: unset;
		bottom: anchor(bottom);
		right: anchor(right);
	}
</style>
