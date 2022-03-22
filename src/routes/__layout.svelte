<script>
	import '../styles/global.css'
	import Title from "$lib/components/Title.svelte";

</script>

<header>
	<Title title="Epic Gaming Guides"/>
</header>
<main>
	<slot/>
</main>
<footer>
	<p>Copyright 2022 Epic Gaming Guides</p>
</footer>

<style>
	header {
		display: flex;
		justify-content: center;
	}

	main {
		max-width: 960px;
		margin: 20px auto;
	}
</style>