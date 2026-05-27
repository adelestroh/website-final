<script>
	import Index from '$lib/components/Index.svelte';

	import Image22 from '$lib/assets/content/images/22.05.png';
	import Live22 from '$lib/assets/content/audios/Live_22.05.mp3';

	import Image24 from '$lib/assets/content/images/24.05.png';
	import Live24 from '$lib/assets/content/audios/Live-24.05.mp3';

	import Image25 from '$lib/assets/content/images/25.05.png';
	import Live25 from '$lib/assets/content/audios/Live-25.05.mp3';

	import Placeholder from '$lib/assets/content/images/placeholder.png';
</script>

<div id="indexes">
	<p>Location: Strandeiland, Amsterdam, NL</p>
	<Index
		time="52.356100, 5.014607 | 22.05.26 | 7:00 "
		temperature={22}
		weatherID={2}
		src={Image22}
		audioSrc={Live22}
	>
		<p>
			Dragged, dredged, layered - these episodes trace the shifting material reality of the
			shoreline at Strandeiland, an artificial island located in IJBurg. Listening to the material
			reality of sand and its surrounding, I follow
		</p>
	</Index>
	<Index
		time="52.356100, 5.014607 | 24.05.26 | 8:55"
		temperature={17}
		weatherID={3}
		src={Image24}
		audioSrc={Live24}
	>
		<p>
			Dragged, dredged, layered - these episodes trace the shifting material reality of the
			shoreline at Strandeiland, an artificial island located in IJBurg. Listening to the material
			reality of sand and its surrounding, I follow
		</p>
	</Index>
	<Index
		time="52.358302, 5.024382 | 25.04.26 | 10:40"
		temperature={27}
		weatherID={3}
		src={Image25}
		audioSrc={Live25}
	>
		<p>
			Dragged, dredged, layered - these episodes trace the shifting material reality of the
			shoreline at Strandeiland, an artificial island located in IJBurg. Listening to the material
			reality of sand and its surrounding, I follow
		</p>
	</Index>
	<Index time="Scheduled | 12.06.26 | 0:00" temperature={-20} weatherID={0} src={Placeholder}>
		<p>This recording is scheduled, come back later!</p>
	</Index>
	<Index time="Scheduled | 13.06.2026 | 0:00" temperature={-20} weatherID={0} src={Placeholder}>
		<p>This recording is scheduled, come back later!</p>
	</Index>
</div>

<style>
	#indexes {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		gap: 10px;
		padding: 10px 10px 60vh 10px;
		box-sizing: border-box;
		overflow-y: auto;
	}

	p {
		padding-left: 10px;
	}
</style>
