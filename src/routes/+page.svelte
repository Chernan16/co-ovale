<script>
  import Header from "../components/Header.svelte";
  import Note from "../components/Note.svelte";
  import NewNote from "../components/NewNote.svelte";
  import { v4 as uuidv4 } from 'uuid';
  
  let notes = [
   	{
      id: 0,
      title: "Vacaciones",
      color: "blue",
      text: "Hola, como estas? Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
    },
    {
      id: 1,
      title: "Sin Esperanzas",
      color: "yellow",
      text: "NI ILUCIONES!!",
    },
    {
      id: 2,
      title: "vacaciones",
      color: "yellow",
      text: "NO LLORAR EN EL PROCESO",
    },
    {
      id: 3,
      title: "Solicitud",
      color: "fuchsia",
      text: "INTENTO 40MIL",
    },
    {
      id: 4,
      title: "vacaciones",
      color: "indigo",
      text: "Hola, como estas?",
    },
    {
      id: 5,
      title: "vacaciones",
      color: "cyan",
      text: "YA NO AGUANTO MAAAAAASSSSSSSSSSSSSSSSSSSS",
    },
  ];

  function handleAddNote() {
    const id = uuidv4();
    const newNote = {
      id: id,
      title: '',
      color: '',
      text: ''
    };
    notes = [newNote, ...notes];
  }

  
</script>

<main class="bg-gray-100 h-screen parent">
  <div class="bg-white p-5 formulario">
    <Header />
    <div class="flex justify-end">{notes.length} notas</div>
    <div class="flex justify-center">
      <NewNote on:click={handleAddNote} />
    </div>
    
  </div>

  <div class="p-5 flex justify-start items-start content-start flex-wrap gap-4">
    {#each notes as { id, title, color, text }}
      <Note {id} {title} {color} {text} on:updateNota on:color on:remove/>
    {/each}
  </div>
</main>

<style>
  .parent {
    display: grid;
    grid-template-columns: 1fr 2fr;
    grid-template-rows: 1fr;
    grid-column-gap: 0px;
    grid-row-gap: 0px;
  }
</style>
