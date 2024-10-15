<!-- src/routes/+layout.svelte -->
<script>
    import { updated } from '$app/stores';
  </script>
  
  <main data-sveltekit-reload={$updated ? '' : 'off'}>
    <slot />
  </main>