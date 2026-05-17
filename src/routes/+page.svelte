<script>
	import Index from '$lib/components/Index.svelte';
	import Image from '$lib/assets/content/image_station_2.jpeg';
</script>

<div id="indexes">
	<Index time="20.03.26 // 09:55" src={Image}>
		<p>
			Dragged, dredged, layered - these episodes trace the shifting material reality of the
			shoreline at Strandeiland, an artificial island located in IJBurg. Listening to the material
			reality of sand and its surrounding, I follow
		</p>
	</Index>
	{#each { length: 28 }}
		<Index time="17.05.26 // 13:45" src={Image}>
			<p>Dragged, dredged, layered</p>
		</Index>
	{/each}
</div>

<style>
	#indexes {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		gap: 10px;
		padding: 10px;
		box-sizing: border-box;
		overflow-y: auto;
	}
</style>
