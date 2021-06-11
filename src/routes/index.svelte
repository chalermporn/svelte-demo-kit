<script context="module" lang="ts">
  export const prerender = true
</script>

<script lang="ts">
  import Counter from '$lib/Counter/index.svelte'
	c
</script>

<svelte:head>
  <title>Home</title>
</svelte:head>

<section>
  <h1>Home</h1>
	<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate beatae quos ipsum deserunt fugit quo earum excepturi suscipit nobis non ducimus, provident sequi, rem ullam deleniti quas exercitationem vitae quod.</p>
	<div class="flex justify-center w-full">
		<Counter/>
	</div>
</section>
