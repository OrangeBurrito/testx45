<script context="module">
	export async function load() {
		const res = await fetch('https://jsonplaceholder.typicode.com/posts')
		const guides = await res.json()

		if (res.ok) {
			return {
				props: {
					guides
				}
			}
		}
		return {
			status: res.status,
			error: new Error("could not fetch the guides")
		}
	}

</script>

<script>
	export let guides
</script>


<div class="guides">
	<ul>
		{#each guides as guide}
			<li>
				<a sveltekit:prefetch href={`/guides/${guide.id}`}>{guide.title}</a>
			</li>
		{/each}
	</ul>
</div>

<style>
	ul{
		list-style-type: none;
	}

	a {
		display: inline-block;
		margin-top: 10px;
		border: 1px dotted rgba(255,255,255,0.2);
		padding: 1rem;
	}
</style>