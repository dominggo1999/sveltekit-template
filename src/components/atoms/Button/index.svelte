<script lang="ts">
	import { cva, type VariantProps } from 'class-variance-authority';

	const button = cva(
		'bg-orange-500 enabled:hover:bg-orange-600 text-white rounded disabled:opacity-50 disabled:cursor-not-allowed',
		{
			variants: {
				size: {
					small: 'px-2 py-1',
					medium: 'px-3 py-2',
					large: 'px-4 py-3'
				}
			},
			defaultVariants: {
				size: 'medium'
			}
		}
	);

	type ButtonProps = VariantProps<typeof button>;

	export let disabled = false;
	export let size: ButtonProps['size'] = 'medium';
</script>

<button {disabled} class={button({ size })} on:click>
	<slot />
</button>
