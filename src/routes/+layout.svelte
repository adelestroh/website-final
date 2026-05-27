<script lang="ts">
	import '$lib/css/reset.css';
	import '$lib/css/style.css';

	import Map from '$lib/components/Map.svelte';
	import Radio from '$lib/components/Radio.svelte';

	let { children } = $props();
</script>

<div class="bg-image"></div>


<Radio></Radio>

<div id="main-content">
	{@render children()}
	<Map></Map>
</div>

<style>
	:global(body) {
		width: 100vw;
		height: 100dvh;
		margin: unset;
		display: flex;
		flex-direction: column;
		overflow: hidden;
	}

	#main-content {
		width: 100%;
		min-height: 0;
		overflow: hidden;
		height: calc(100vh - 50px);
		display: grid;
		grid-template-columns: auto 300px;
	}

	@media (max-width: 750px) {
		#main-content {
			grid-template-columns: unset;
			grid-template-rows: minmax(0, 1fr) 200px;
		}
	}

	.bg-image
	 {
		position: fixed;
		inset: 0;
		pointer-events: none;
	}

	/* base blur background */
	.bg-image {
		background: url('$lib/assets/background/background_img.png') center/cover;
		transform: scale(1.1);
		z-index: -5;
	}

	
</style>
