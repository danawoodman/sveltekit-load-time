<script context="module">
	export async function load({ fetch }) {
		const start = Date.now();
		const res = await fetch('https://jsonplaceholder.typicode.com/todos');
		const json = await res.json();
		const elapsed = Date.now() - start;
		console.log({ elapsed, start });
		return { props: { json, start, elapsed } };
	}
</script>

<script lang="ts">
	// export let json;
	export let elapsed;
	export let start;
</script>

<ul>
	<li>Elapsed: {elapsed}</li>
	<li>Start: {start}</li>
</ul>

<!-- <pre>{JSON.stringify(json, null, 2)}</pre> -->
