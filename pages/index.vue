<script setup>
	let currentData = ref(null);
	const { data, error } = await useFetch("../api/my-data", {
		method: "GET",
	}); // Fetch data from the API route
	console.log(data.value);
	if (!error.value) {
		currentData.value = data.value;
	}
</script>

<template>
	<div class="hero">
		<img
			src="/img/surfclock.jpg"
			alt="surfclock"
			class="hero-image"
		/>
		<h1>Coming soon</h1>
	</div>
</template>

<style>
body{
    margin: 0px;
    max-width: 100vw;
    overflow-x: hidden;
}
	.hero {
		height: 100%;
		display: flex;
		justify-content: center;
	}
	h1 {
		font-size: 70px;
		color: white;
		font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
			"Lucida Sans Unicode", Geneva, Verdana, sans-serif;
		text-shadow: 2px 2px 15px rgba(0, 0, 0, 0.711);
        text-align: center;
	}

	.hero-image {
		height: 100vh;
		position: absolute;
		z-index: -1;
        min-width: 100vw;
	}
</style>
