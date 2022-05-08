<script lang="ts">
	import './styles/default.css';
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	export let size: 'small' | 'medium' | 'large' = 'medium';
	export let type: 'outlined' | 'contained' | 'error' | 'text' = 'text';
	export let loading: boolean = false;
	export let disabled: boolean = false;

	$: clickable = !disabled && !loading;

	function onClick() {
		if (clickable) {
			dispatch('click');
		}
	}
</script>

<button
	class="bui size-{size} type-{type} {loading && 'state-loading'}"
	on:click={onClick}
	disabled={!clickable}
>
	<slot />
</button>

<style>
	button {
		cursor: pointer;
		background-color: var(--on-surface);
		border: none;
		padding: 5px;
		border-radius: 4px;
		transition: background-color 0.2s;

		color: var(--accent-text);
	}

	button:active {
		background-color: red;
		transition: background-color 0s;
	}

	.size-small {
		font-size: 0.8rem;
	}

	.size-medium {
		font-size: 1rem;
	}
	.size-large {
		font-size: 1.2rem;
	}
</style>
