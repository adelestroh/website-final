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
		{#if !isError}
			{#if isPlaying}
				<svg
					viewBox="-1 0 8 8"
					version="1.1"
					xmlns="http://www.w3.org/2000/svg"
					xmlns:xlink="http://www.w3.org/1999/xlink"
					fill="currentColor"
					><g id="SVGRepo_iconCarrier">
						<g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
							<g
								id="Dribbble-Light-Preview"
								fill="currentColor"
								transform="translate(-67.000000, -3765.000000)"
							>
								<g id="icons" transform="translate(56.000000, 160.000000)">
									<path
										d="M11,3613 L13,3613 L13,3605 L11,3605 L11,3613 Z M15,3613 L17,3613 L17,3605 L15,3605 L15,3613 Z"
										id="pause-[#1010]"
									>
									</path>
								</g>
							</g>
						</g>
					</g></svg
				>
			{:else}
				<svg
					viewBox="-0.5 0 8 8"
					version="1.1"
					xmlns="http://www.w3.org/2000/svg"
					xmlns:xlink="http://www.w3.org/1999/xlink"
					fill="currentColor"
					><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g
						id="SVGRepo_tracerCarrier"
						stroke-linecap="round"
						stroke-linejoin="round"
					></g><g id="SVGRepo_iconCarrier">
						<title>play [#1001]</title> <desc>Created with Sketch.</desc> <defs> </defs>
						<g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
							<g
								id="Dribbble-Light-Preview"
								fill="currentColor"
								transform="translate(-427.000000, -3765.000000)"
							>
								<g id="icons" transform="translate(56.000000, 160.000000)">
									<polygon id="play-[#1001]" points="371 3605 371 3613 378 3609"> </polygon>
								</g>
							</g>
						</g>
					</g></svg
				>
			{/if}
		{:else}
			<svg
				viewBox="-1 0 18 18"
				version="1.1"
				xmlns="http://www.w3.org/2000/svg"
				xmlns:xlink="http://www.w3.org/1999/xlink"
				fill="currentColor"
				><g id="SVGRepo_bgCarrier" stroke-width="0"></g><g
					id="SVGRepo_tracerCarrier"
					stroke-linecap="round"
					stroke-linejoin="round"
				></g><g id="SVGRepo_iconCarrier">
					<title>arrow_repeat [#236]</title> <desc>Created with Sketch.</desc> <defs> </defs>
					<g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
						<g
							id="Dribbble-Light-Preview"
							fill="currentColor"
							transform="translate(-302.000000, -7080.000000)"
						>
							<g id="icons" transform="translate(56.000000, 160.000000)">
								<path
									d="M260,6930 C260,6933 257.308,6936 254,6936 C250.692,6936 248,6933.308 248,6930 C248,6926.692 250.692,6924 254,6924 L254,6926 L259,6923 L254,6920 L254,6922 C249.582,6922 246,6925.582 246,6930 C246,6934.418 249.582,6938 254,6938 C258.418,6938 262,6935 262,6930 L260,6930 Z"
									id="arrow_repeat-[#236]"
								>
								</path>
							</g>
						</g>
					</g>
				</g></svg
			>
		{/if}
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
