<script>
	import { page } from '$app/stores';
	import RouteContainer from '../components/RouteContainer.svelte';
	let videoId = $page.url.searchParams.get('v');
</script>

<svelte:head>
	<title>Watch - MooTube</title>
</svelte:head>

<RouteContainer>
	<iframe
		width="600"
		height="400"
		src={`https://www.youtube-nocookie.com/embed/${videoId}?rel=0&modestbranding=1`}
		title="YouTube video player"
		frameborder="0"
		allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
		allowfullscreen
	/>
</RouteContainer>
