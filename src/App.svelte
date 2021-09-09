<script lang="ts">
	import { Router, Link, Route } from "svelte-navigator";
	import IceCreamMenus from "./routes/IceCreamMenus.svelte"
	import BoundTextArea from "./routes/BoundTextArea.svelte"
	import WritableStores from "./routes/WritableStores.svelte"
	import Tweening from "./routes/Tweening.svelte"

	const data = [
		{
			component: IceCreamMenus,
			link: "/IceCreamMenus",
			text: 'Ice Cream Menus'
		},
		{
			component: BoundTextArea,
			link: '/BoundTextArea',
			text: 'Bound Text Area'
		},
		{
			component: WritableStores,
			link: '/WritableStores',
			text: 'Writable Stores'
		},
		{
			component: Tweening,
			link: '/Tweening',
			text: 'Tweening'
		}
	];

</script>

<Router>
	<h1>Components:</h1>
	<nav>
		{#each data as d}
			<Link to={d.link}>{d.text}</Link>
		{/each}
	</nav>

	<div>
		<Route path="/">Home</Route>

		{#each data as d}
			<Route path={d.link} component={d.component} />
		{/each}
	</div>

	{#each data as d}
		<h2><a href={d.link} target="_blank" class="cursor-pointer">{d.text}</a></h2>
	{/each}
</Router>