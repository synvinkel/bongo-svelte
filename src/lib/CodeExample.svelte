<script lang="ts">
	export let label: string = 'Code';
</script>

<details>
	<summary>{label}</summary>
	<pre>
        <slot />
    </pre>
</details>

<style>
    summary {
        cursor: pointer;
    }

    pre {
        background: #333;
        border-radius: 3px;
        color: white;
    }
</style>