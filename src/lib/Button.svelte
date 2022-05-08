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
		display: inline-block;
		position: relative;
		user-select: none;
		outline: none;
		-webkit-tap-highlight-color: rgba(0, 0, 0, 0);

		background-color: rgba(0, 0, 0, 0);

		cursor: pointer;
		border: none;
		padding: 5px;
		border-radius: 4px;
		color: var(--accent-text);
	}

	button:disabled {
		cursor: not-allowed;
	}

	.type-outlined {
		background-color: var(--background);
		border: solid 1px var(--accent);
	}

	.type-contained {
		background-color: var(--accent-surface);
		color: var(--on-accent);
	}

	.state-loading {
		border: solid 1px var(--container-outline-lighter);
	}

	.size-small {
		font-size: 14px;
		height: 30px;
		padding: 0 10px;
	}

	.size-medium {
		font-size: 16px;
		height: 40px;
		padding: 0 15px;
	}
	.size-large {
		font-size: 18px;
		height: 50px;
		padding: 0 25px;
	}
</style>
