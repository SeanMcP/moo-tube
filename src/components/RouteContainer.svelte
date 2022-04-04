<script>
	import Content from './Content.svelte';
</script>

<div class="route">
	<header>
		<Content>
			<h1>
				<a href="/"><span>Moo</span><span>Tube</span></a>
			</h1>
		</Content>
	</header>
	<main>
		<Content>
			<slot />
		</Content>
	</main>
	<footer>
		<Content>
			Built especially for <a href="https://smcp.dev/sam">Sam</a>
		</Content>
	</footer>
</div>

<style>
	.route {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}
	header {
		background-color: #202020;
	}
	h1 {
		margin: 0;
		font-size: 125%;
	}
	main {
		flex-grow: 1;
	}
	footer {
		background-color: #0f0f0f;
	}
	header a {
		color: white;
		font-family: 'Roboto Condensed', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
			Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
		text-decoration: none;
	}
	header a span:first-child {
		background-color: #ff0000;
		border-radius: 10%;
		padding: 0.25rem 0.5rem;
		margin-right: 2px;
	}
</style>
