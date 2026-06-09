<script lang="ts">
	import { onMount } from 'svelte';

	let mapContainer: HTMLDivElement;
	let L: typeof import('leaflet');

	onMount(async () => {
		L = await import('leaflet');

		const lat = 52.356100;
		const lng = 5.014607;

		// Create map
		const map = L.map(mapContainer).setView([lat, lng], 15);

		// Add tiles
		L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
			attribution: '&copy; OpenStreetMap'
		}).addTo(map);

		const marker = L.marker([lat, lng]).addTo(map)

		// FIX 1: force Leaflet to recalc size (VERY important in Svelte/layouts)
		setTimeout(() => {
			map.invalidateSize();
		}, 0);

		// FIX 2: ensure marker icons always load correctly in Vite/Svelte
		const icon = L.icon({
			iconUrl: 'https://unpkg.com/leaflet@1.6.0/dist/images/marker-icon.png',
			shadowUrl: 'https://unpkg.com/leaflet@1.6.0/dist/images/marker-shadow.png',
			iconSize: [25, 41],
			iconAnchor: [12, 41],
			popupAnchor: [1, -34],
			shadowSize: [41, 41]
		});

		map.setView([lat, lng],15);

		// Add marker
		L.marker([lat, lng], { icon })
			.addTo(map)
			.bindPopup('transmission station')
			.openPopup();

		// Debug (optional but useful)
		console.log('Center:', map.getCenter());
	});
</script>

<!-- Leaflet CSS -->
<link
	rel="stylesheet"
	href="https://unpkg.com/leaflet@1.6.0/dist/leaflet.css"
	integrity="sha512-xwE/Az9zrjBIphAcBb3F6JVqxf46+CDLwfLMHloNu6KEQCAWi6HcDUbeOfBIptF7tcCzusKFjFw2yuvEpDL9wQ=="
	crossorigin=""
/>

<div id="map-column">
	<p>Current Location:</p>
	<div id="map" bind:this={mapContainer}></div>
</div>

<style>
	#map-column {
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		padding: 10px;
		gap: 10px;
		height: 100%;
		min-height: 0;
		z-index: 1;
		backdrop-filter: blur(4px);
	}

	#map {
		width: 100%;        
		aspect-ratio: 1 / 1;
		max-height: 100%;
		box-sizing: border-box;
		border-radius: 25px;
		overflow: hidden;   
	}
</style>
