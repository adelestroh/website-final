<script lang="ts">
	import { onMount } from 'svelte';

	let mapContainer: HTMLDivElement;
	let L: typeof import('leaflet');

	onMount(async () => {
		L = await import('leaflet');
		let map = L.map(mapContainer).setView([52.3417, 4.8738], 15);

		L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
			attribution: '&copy; OpenStreetMap'
		}).addTo(map);
	});
</script>

<link
	rel="stylesheet"
	href="https://unpkg.com/leaflet@1.6.0/dist/leaflet.css"
	integrity="sha512-xwE/Az9zrjBIphAcBb3F6JVqxf46+CDLwfLMHloNu6KEQCAWi6HcDUbeOfBIptF7tcCzusKFjFw2yuvEpDL9wQ=="
	crossorigin=""
/>

<div id="map" bind:this={mapContainer}></div>

<style>
	#map {
		width: auto;
		aspect-ratio: 1 / 1;
		margin: 10px;
		box-sizing: border-box;
		align-self: flex-end;
		border-radius: 25px;
	}
</style>
