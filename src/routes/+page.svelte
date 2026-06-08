<script>
	import Index from '$lib/components/Index.svelte';

	import Image22 from '$lib/assets/content/images/Img_22.05..jpeg';
	import Live22 from '$lib/assets/content/audios/Live_22.05.mp3';

	import Image24 from '$lib/assets/content/images/24.05.png';
	import Live24 from '$lib/assets/content/audios/Live-24.05.mp3';

	import Image25 from '$lib/assets/content/images/Img_05.06..jpeg';
	import Live25 from '$lib/assets/content/audios/MP3_05.06. Live.mp3';

	import Image26 from '$lib/assets/content/images/Img_07.06..jpeg';
	import Live26 from '$lib/assets/content/audios/MP3_07.06.NEU.mp3';

	import Placeholder from '$lib/assets/content/images/placeholder.png';
</script>

<div id="indexes">
	<p>Location: Strandeiland, Amsterdam, NL</p>
	<Index
		time=" 22.05.2026 | 7:00 (CEST) "
		temperature={22}
		weatherID={3}
		src={Image22}
		audioSrc={Live22}
	>
		<p>
		Streaming live from a small strip of shoreline on Strandeiland, one of the few sections of this artificial island still temporarily accessible to the public, this episode taps into the sonic reality of a place in the midst of massive transformation. Early morning drilling, water pumps, the ground being split open for sewage infrastructure: the construction that is actively reshaping this island reaches you through four microphone channels, each offering a different opening into the landscape. 
Eventough the water surface looks calm and the water is perfectly clear, the hydrophone captures pulses underwater, potentially travelling and being transmitted from the drilling site nearby making perceptible how far the effects of the construction site reaches and makes clear that not only has an impact on the island itself, but also the surrounding water and eco systems.
While the water's surface appears calm and remarkably clear, the hydrophone captures rhythmic pulses beneath it, likely transmitted from the nearby drilling operations. These underwater vibrations make perceptible the far-reaching effects of construction activity, extending well beyond the visible worksite.
		</p>
		<p> #zoommic #hydrophone #contactmic #binauralelectretmic

		</p>
	</Index>
	<Index
		time="24.05.2026 | 8:55 (CEST)"
		temperature={17}
		weatherID={3}
		src={Image24}
		audioSrc={Live24}
	>
		<p>
			Returning to the same strip of shoreline on Strandeiland two days later, you can listen for what has changed at this location — and what hasn't. Focusing on the dredged sand as displaced material bringing Strandeiland into existence, you tap into its sonic realm. You're not only listening to matter, but a displaced eco system, an extracted part of IJsselmeer's lakebed that has been commodified to generate real estate and leisure for the city of Amsterdam. This stream took place on a Sunday, so through the absence of the construction site, you are able to hear what remains of Strandeiland's sonic reality.
		</p>
		<p>#zoommic #hydrophone #subsurfacemic #binauralelectretmic</p>

	</Index>
	<Index
		time="05.06.2026 | 11:24 (CEST)"
		temperature={17}
		weatherID={1}
		src={Image25}
		audioSrc={Live25}
	>
		<p>
			Although the construction site is active today, the rough weather conditions make it difficult to distinguish which sounds and signals are being transmitted through the water from the nearby drilling operations. Strong winds agitate the surface, generating fast-moving waves and a dense accumulation of white foam along the shoreline. The weather is especially present in the soundscape, dominating all four microphone channels with the force of the wind and the constant motion of the water.
As a result, the boundary between environmental and industrial sound becomes less clear. It is difficult to determine where the effects of the weather end and those of the construction activity begin. Yet the acoustic character of the site differs noticeably from previous livestreams made under calmer conditions, when construction sounds were more clearly perceptible. Today's transmission reveals how weather can shape, mask, and transform the audibility of human activity, producing a markedly different listening experience of the same location.
		</p>
		<p>#zoommic #hydrophone #contactmic #binauralelectretmic</p>
	</Index>

<Index
		time="07.06.2026 | 11:24 (CEST)"
		temperature={17}
		weatherID={0}
		src={Image26}
		audioSrc={Live26}
	>
		<p>
		Add text here
		</p>
		<p>#zoommic #hydrophone #contactmic #binauralelectretmic</p>
	</Index>

	<Index
		time="09.06.2026 | 10:00 (CEST)"
		temperature={17}
		weatherID={1}
		src={Image25}
		audioSrc={Live25}
	>
		<p>
		Add text here
		</p>
		<p>#zoommic #hydrophone #contactmic #binauralelectretmic</p>
	</Index>
	

	
	<Index time="Scheduled | 12.06.26 | 0:00" temperature={-20} weatherID={0} src={Placeholder}>
		<p>This recording is scheduled, come back later!</p>
	</Index>
	<Index time="Scheduled | 13.06.26 | 0:00" temperature={-20} weatherID={0} src={Placeholder}>
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
