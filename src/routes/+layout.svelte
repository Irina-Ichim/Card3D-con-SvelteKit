<script>
	import Header from './Header.svelte';
	import './styles.css';
	import '../components/CustomBackground.svelte';
  import CustomBackground from '../components/CustomBackground.svelte';
	import Card from '../components/Card.svelte';


	let isMouseEntered = false; // o el valor inicial que desees
</script>

<div class="app">
	<CustomBackground className="custom-background" />

	<Header />

	<Card {isMouseEntered} />


	<main>
		<slot />
	</main>

	<footer>
		<p>visit <a href="https://irina-ichim.com">Irina Ichim</a></p>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
