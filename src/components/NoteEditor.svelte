

<script>
    export let note;
    export let onSave;
  
    let updatedTitle = note.title;
    let updatedText = note.text;
  
    function handleSave() {
      onSave(note.id, updatedTitle, updatedText);
    }
  </script>
  
  <div class="NotePlaceholder">
    <input type="text" placeholder="Título" bind:value={updatedTitle} class="border p-2 mb-2">
    <textarea placeholder="Texto" bind:value={updatedText} rows="4" class="border p-2 mb-2"></textarea>
    <button on:click={handleSave}>Guardar</button>
  </div>
  
  <style>
    button {
      cursor: pointer;
      border-radius: 0px;
      color: #bbb;
      border: dotted 0px #ccc;
      background-color: transparent;
      font-weight: bold;
      width: 10%;
      height: 5px;
    }
  </style>
  