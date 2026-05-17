<script lang="ts">
	let audioElement: HTMLAudioElement | null = $state(null);
	let isPlaying = $state(false);
	let isError = $state(false);

	const streamUrl = 'https://pub.sandberg.nl/live';

	function togglePlay() {
		if (!audioElement) return;

		if (isPlaying) {
			audioElement.pause();
		} else {
			isError = false; // Reset error state on attempt
			audioElement.play().catch(() => {
				isError = true;
			});
		}
		isPlaying = !isPlaying;
	}

	function handleError() {
		console.error('Stream error detected');
		isError = true;
		isPlaying = false;
	}
</script>

<audio
	bind:this={audioElement}
	src={streamUrl}
	onpause={() => (isPlaying = false)}
	onplay={() => (isPlaying = true)}
	onerror={handleError}
></audio>

<div class="controls">
	<button onclick={togglePlay}>
		{isError ? 'Retry' : isPlaying ? '❚❚' : '▶'}
	</button>

	<div class="status">
		{#if isError}
			<p class="offline">OFFLINE (Error)</p>
		{:else if isPlaying}
			<p class="live">LIVE</p>
		{:else}
			<p class="idle">READY</p>
		{/if}
	</div>
</div>

<style>
	.controls {
		width: 100%;
		display: flex;
		gap: 20px;
		align-items: center;
		height: 50px;
		padding: 20px;
		background: rgba(171, 165, 153, 0.249);
		backdrop-filter: blur(2px);
		z-index: 20;
	}

	button {
		background: unset;
		cursor: pointer;
		width: 20px;
	}
</style>
