<script lang="ts">
	import type { Hst as St } from '@histoire/plugin-svelte';
	import { logEvent } from 'histoire/client';
	import BaseButton from './index.svelte';

	export let Hst: St;

	let disabled = false;
	let size: 'small' | 'medium' | 'large' = 'medium';
</script>

<Hst.Story title="Button">
	<BaseButton {disabled} size="small" on:click={(event) => logEvent('click', event)}>
		Small
	</BaseButton>

	<BaseButton {disabled} {size} on:click={(event) => logEvent('click', event)}>Medium</BaseButton>

	<BaseButton {disabled} size="large" on:click={(event) => logEvent('click', event)}>
		Large
	</BaseButton>
	<div style="margin-top: 6px;">
		<label>
			<input type="checkbox" bind:checked={disabled} />
			Disabled
		</label>
	</div>

	<svelte:fragment slot="controls">
		<Hst.Checkbox bind:value={disabled} title="Disabled" />
	</svelte:fragment>
</Hst.Story>
