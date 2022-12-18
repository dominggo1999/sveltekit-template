<script lang="ts">
	import { Button } from '../components/atoms';
</script>

<h1 class="text-3xl font-bold underline">Hello world!</h1>

<p class="text-red-500">
	Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vero, blanditiis.
</p>

<Button size="small" on:click={(event) => console.log(event)}>Hello World</Button>
