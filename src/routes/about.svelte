<script context="module">
  import { browser, dev } from '$app/env'

  // we don't need any JS on this page, though we'll load
  // it in dev so that we get hot module replacement...
  export const hydrate = dev

  // ...but if the client-side router is already loaded
  // (i.e. we came here from elsewhere in the app), use it
  export const router = browser

  // since there's no dynamic data here, we can prerender
  // it so that it gets served as a static asset in prod
  export const prerender = true

</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<div class="">
  <div class="font-medium text-5xl mb-2">About</div>
  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Enim laudantium facere dolorem nemo culpa voluptatum reprehenderit voluptas magnam quo assumenda repudiandae, quis atque pariatur quae. Doloremque id cumque ipsam illo.</p>
</div>
