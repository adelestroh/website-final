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
			Streaming live from a small strip of shoreline on Strandeiland, one of the few sections of this artificial island still temporarily accessible to the public, this episode taps into the sonic reality of a place in the midst of massive transformation. Early morning drilling, water pumps, the ground being split open for sewage infrastructure: the construction that is actively reshaping this island reaches you through four microphone channels, each offering a different opening into the landscape. 
What arrives through your headphones is not Strandeiland itself. It is a partial reconstruction, one of many versions: filtered through microphones, signal loss, and the limitations of this streaming station. But even in its incompleteness, this stream captures something the dominant narrative of this island does not: the sound of a place being fundamentally and irreversibly remade. 
		</p>
		<p> #zoommic #hydrophone #contactmic #binauralelectretmic

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
			Returning to the same strip of shoreline on Strandeiland two days later, you can listen for what has changed at this location — and what hasn't. Focusing on the dredged sand as displaced material bringing Strandeiland into existence, you tap into its sonic realm. You're not only listening to matter, but a displaced eco system, an extracted part of IJsselmeer's lakebed that has been commodified to generate real estate and leisure for the city of Amsterdam. This stream took place on a Sunday, so through the absence of the construction site, you are able to hear what remains of Strandeiland's sonic reality.
		</p>
		<p>#zoommic #hydrophone #subsurfacemic #binauralelectretmic</p>

	</Index>
	<Index
		time="52.358302, 5.024382 | 25.04.26 | 10:40"
		temperature={27}
		weatherID={3}
		src={Image25}
		audioSrc={Live25}
	>
		<p>
			By sneaking into a hole in the fence of the construction site, you are able to listen to exclusive content streamed from Het Oog, an artifical body of water sitting on top of a primeval water channel. The entire landscape here is an assembly of displaced materials, a place constructed out of other places. Listening to it means listening to multiple elsewheres at once — and to the ghost of a river that once shaped this ground before it was built on top over.
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
