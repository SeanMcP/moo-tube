<script>
	import RouteContainer from '../components/RouteContainer.svelte';
	import videos from '../videos.json';

	console.log(videos);
</script>

<svelte:head>
	<title>MooTube</title>
</svelte:head>

<RouteContainer>
	{#each Object.entries(videos) as [title, ids]}
		<section>
			<h2>{title}</h2>
			<ul>
				{#each ids as id}
					<li>
						<a
							href={'/watch?v=' + id}
							style={`background-image:url(https://img.youtube.com/vi/${id}/default.jpg)`}
						>
							<span class="visually-hidden">Link to {id}</span>
						</a>
					</li>
				{/each}
			</ul>
		</section>
	{/each}
</RouteContainer>

<style>
	h2 {
		margin-top: 2em;
		margin-bottom: 1rem;
	}
	ul {
		list-style-type: none;
		display: grid;
		gap: 0.5rem;
		grid-template-columns: repeat(4, 1fr);
		margin: 0;
		padding: 0;
	}
	li {
		height: 90px;
	}
	a {
		background-position: center;
		background-size: cover;
		display: block;
		height: 100%;
		position: relative;
		width: 100%;
	}
	a:hover::after {
		content: '';
		height: 0.25rem;
		background-color: currentColor;
		position: absolute;
		left: 0;
		bottom: 0;
		right: 0;
	}
</style>
