<script>
	import Header from './Header.svelte';
	import './styles.css';
</script>

<div class="bg-black min-h-screen flex flex-col items-center">
	<Header />

	<main class="flex w-full p-4 m-4 justify-center grow text-white bg-black">
		<slot />
	</main>

	<footer class="text-white">
		<p>Made with ❤️ by ICX</p>
	</footer>
</div>
