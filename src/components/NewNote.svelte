<script>
  // No necesitas importar 'uuid' ni definir 'notes' aquí
  // La lógica de agregar notas se manejará en la página 'index.svelte'
  
  // No necesitas la función 'handleAddNote()' aquí, se manejará en la página 'index.svelte'
</script>

<div class="NewNote">
  <button on:click>AddNote</button>
</div>

<style>
  button {
    cursor: pointer;
    border-radius: 10px;
    color: #bbb;
    border: dotted 5px #ccc;
    background-color: transparent;
    font-weight: bold;
    width: 450px;
    height: 400px;
  }

  button:hover {
    color: rgb(35, 58, 134);
    border: dotted 5px rgb(31, 101, 167);
    background-color: rgb(223, 139, 255);
  }
</style>
