<script lang="ts">
    import { updated } from '$app/stores';
	import { beforeNavigate } from '$app/navigation';
	import { VERSION } from '$lib/version';

    beforeNavigate(({ willUnload, to }) => {
		// Only execute if redirection is enabled
		if ($updated && !willUnload && to?.url) {
            console.log('Before navigate will reload');
			location.href = to.url.href;
		}
	});


</script>

<h1>Welcome to SvelteKit</h1>
<p>Let's see if we can reproduce preload css. v={VERSION}</p>

updated=<span>{$updated}</span>

<div style="display: flex; flex-direction: column">
    <a href="/foo-bar" data-sveltekit-preload-data="hover">Foo-bar page (data-sveltekit-preload-data="hover")</a>
    <a href="/foo-bar">Foo-bar page (no tags)</a>
    <a href="/foo-bar" data-sveltekit-reload>Foo-bar page (data-sveltekit-reload)</a>
</div>


<style>

    a {
        margin-top: 20px;
    }
</style>