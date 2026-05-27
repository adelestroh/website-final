<script lang="ts">
	let { image, sound }: { image: string; sound?: string } = $props();

	let audioSource: HTMLAudioElement | undefined = $state();
	let isPlaying = $state(false);
</script>

<button
	id="sound-player"
	class={sound ? '' : 'noAudioSrc'}
	onclick={(e) => {
		if (sound) {
			e.preventDefault();
			e.stopPropagation();
		}

		if (isPlaying) {
			audioSource!.pause();
			audioSource!.currentTime = 0;
			isPlaying = !isPlaying;
		} else {
			audioSource!.play();
			isPlaying = !isPlaying;
		}
	}}
>
	<img src={image} alt="" />
	<audio bind:this={audioSource} loop src={sound}></audio>
	{#if sound}
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
	{/if}
</button>

<style>
	#sound-player {
		width: 100%;
		height: 100%;
		padding: 10px;
		display: flex;
		flex-direction: column;
		justify-content: flex-start;
		cursor: pointer;
		position: relative;
		background: unset;

		svg {
			position: absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
			width: 50px;
		}
	}

	.noAudioSrc {
		cursor: default !important;
	}
</style>
