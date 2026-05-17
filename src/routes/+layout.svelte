<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import '$lib/css/reset.css';
	import '$lib/css/style.css';

	import Map from '$lib/components/Map.svelte';
	import Radio from '$lib/components/Radio.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="bg-image"></div>
<div class="bg-png"></div>
<div class="bg-png-2"></div>
<div class="bg-png-3"></div>
<div class="bg-png-4"></div>
<div class="bg-splitter-1"></div>
<div class="bg-splitter-2"></div>

<Radio></Radio>

<div id="main-content">
	{@render children()}
	<Map></Map>
</div>

<style>
	:global(body) {
		width: 100vw;
		height: 100vh;
		margin: unset;
		/* overflow: hidden; */
		display: flex;
		flex-direction: column;
	}

	#main-content {
		width: 100%;
		height: calc(100vh - 50px);
		display: grid;
		grid-template-columns: auto 300px;
	}

	.bg-image,
	.bg-png,
	.bg-png-2,
	.bg-png-3,
	.bg-png-4,
	.bg-splitter-1,
	.bg-splitter-2 {
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

	/* floating PNG layers */
	.bg-png {
		background: url('$lib/assets/background/3D_Shape_1.png') center/cover;
		z-index: -4;
	}
	.bg-png-2 {
		background: url('$lib/assets/background/3D_Shape_2.png') center/150%;
		z-index: -4;
	}
	.bg-png-3 {
		background: url('$lib/assets/background/3D_Shape_3.png') center/cover;
		z-index: -4;
	}
	.bg-png-4 {
		background: url('$lib/assets/background/3D_Shape_4.png') center/cover;
		z-index: -4;
	}

	/* splitters MUST NOT disappear */
	.bg-splitter-1 {
		background: url('$lib/assets/background/splitter_1.png') center/120% no-repeat;
		z-index: -3;
	}

	.bg-splitter-2 {
		background: url('$lib/assets/background/splitter_2.png') center/90% no-repeat;
		z-index: -3;
	}
</style>
