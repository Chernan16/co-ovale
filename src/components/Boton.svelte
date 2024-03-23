<!-- Boton.svelte -->

<script>
    let contador = 0;

    $: total = contador;

    function handleClick() {
        contador++;
    }
</script>

<div class="Boton">
    <button on:click={handleClick}>Click me</button>
    <div>
        has dado {total} clicks
    </div>
</div>

<style>

</style>

