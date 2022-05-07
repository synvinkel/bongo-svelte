<script lang="ts">
	export let size: 'small' | 'medium' | 'large' = 'medium';
</script>

<button class="size-{size}" on:click>
	<slot />
</button>

<style>
	button {
		cursor: pointer;
		background-color: pink;
		border: none;
		padding: 5px;
		border-radius: 4px;
		transition: background-color 0.2s;

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
