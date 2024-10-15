


<script lang="ts">
	import type { PageData } from "./$types";



    

    export let data: PageData;

</script>


<h1>Foo-bar page - message:</h1>
<p>{data.message}</p>



<style>
    /*
    Let's add some css on this page, to check pre-fetching of code/data.
    */
    h1 {
        color: yellow;
        font-size: large;
    }
</style>