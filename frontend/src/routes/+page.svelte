
<script>
	import { onMount } from 'svelte';
import { Card, Button } from "flowbite-svelte";
  import { ArrowRightOutline } from "flowbite-svelte-icons";
let name ="francisco"
let events = $state([])
const addEvent=()=>{
  events.push("event")
    
}
onMount(async () => {
		let data = await fetch('https://api.thecatapi.com/v1/images/search?limit=20').then((x) => x.json());
		events.push(...data)
	});
</script>
<h1>Welcome to SvelteKit {name.toUpperCase()}</h1>
<h1>evenet size: {events.length}</h1>
<div class="grid grid-cols-5 gap-4 items-center">
{#each events as event}
<Card class="p-4 sm:p-6 md:p-8">
  <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{event.id}</h5>
  <p class="mb-3 leading-tight font-normal text-gray-700 dark:text-gray-400">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
  <Button class="w-fit">
    Read more <ArrowRightOutline class="ms-2 h-6 w-6 text-white" />
  </Button>
</Card>
{/each}

	</div>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<button onclick={addEvent}>add event</button>

