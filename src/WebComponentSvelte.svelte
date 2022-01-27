<svelte:options tag="web-component-svelte" />

<script lang="ts">
	import { get_current_component } from "svelte/internal";

  const component = get_current_component();

	function handleClick() {
		component.dispatchEvent(new CustomEvent('button-clicked', { detail: 'Hello from Svelte!' } ));
	}

	export let name: string;
</script>

<div>
	<h1>Hello from Svelte, {name}!</h1>
	<button on:click={handleClick}>Click Me!</button>
	<slot></slot>
</div>

<style>
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4rem;
		font-weight: 100;
	}
</style>
