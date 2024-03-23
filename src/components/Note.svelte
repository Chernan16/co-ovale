<script>
    let notes = [];

    export let title;
    export let color;
    export let text;
    export let id;

    let bg = "";
    let fg = "";
    let colortitulo = "";

    function updateColor(nuevoColor) {
        switch (color) {
            case "yellow":
                bg = "bg-yellow-100";
                fg = "text-yellow-800";
                colortitulo = "text-yellow-900";
                break;
            case "blue":
                bg = "bg-blue-100";
                fg = "text-blue-800";
                colortitulo = "text-blue-900";
                break;
            case "indigo":
                bg = "bg-indigo-300";
                fg = "text-indigo-600";
                colortitulo = "text-indigo-900";
                break;
            case "fuchsia":
                bg = "bg-fuchsia-200";
                fg = "text-fuchsia-800";
                colortitulo = "text-fuchsia-900";
                break;
            case "cyan":
                bg = "bg-cyan-200";
                fg = "text-cyan-800";
                colortitulo = "text-cyan-900";
                break;
        }
    }
    function updateNota(id, nuevoTitulo, nuevoTexto) {
        notes = notes.map((note) => {
            if (note.id === id) {
                return {
                    ...note,
                    title: nuevoTitulo,
                    text: nuevoTexto,
                };
            }
            return note;
        });
    }
    function deleteNota(id) {
        notes = notes.filter((note) => note.id !== id);
    }

    function changeColor(nuevoColor) {
        updateColor(nuevoColor);
        updateNota(id, title, text);
    }
</script>

<div class="relative {bg} w-72 h-1/3 px-5 py-2">
    <input
        type="text"
        bind:value={title}
        class="text-xl font-bold mb-6 {colortitulo} bg-transparent"
    />
    <textarea
        bind:value={text}
        class="ftext-xl font-bold mb-6 {fg} bg-transparent w-full h-1/2"
        maxlength="188"
        style="resize: none;"
    ></textarea>

    
    <button
        class="absolute top-0 right-0 -mt-0.98 -mr-0.98 text-black hover:text-black-700"
        on:click={() => deleteNota(id)}
    >
        <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5"
        >
            <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="m14.74 9-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 0 1-2.244 2.077H8.084a2.25 2.25 0 0 1-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 0 0-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 0 1 3.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 0 0-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 0 0-7.5 0"
            />
        </svg>
    </button>

    <button
        class="absolute top-0 right-5 -mt-0.98 -mr-0.98 text-black hover:text-black-700"
        on:click={() => updateNota(id, title, text)}
    >
        <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-Width="1.5"
            stroke="currentColor"
            class="w-5 h-5"
        >
            <path
                strokeLinecap="round"
                strokeLinejoin="round"
                d="m16.862 4.487 1.687-1.688a1.875 1.875 0 1 1 2.652 2.652L6.832 19.82a4.5 4.5 0 0 1-1.897 1.13l-2.685.8.8-2.685a4.5 4.5 0 0 1 1.13-1.897L16.863 4.487Zm0 0L19.5 7.125"
            />
        </svg>
    </button>

    
    <button
    class="absolute top-0 right-10 -mt-0.98 text-black hover:text-black-700"
    on:click={() => changeColor(id, nuevoColor)} 
>
        <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5"
        >
            <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M9.53 16.122a3 3 0 0 0-5.78 1.128 2.25 2.25 0 0 1-2.4 2.245 4.5 4.5 0 0 0 8.4-2.245c0-.399-.078-.78-.22-1.128Zm0 0a15.998 15.998 0 0 0 3.388-1.62m-5.043-.025a15.994 15.994 0 0 1 1.622-3.395m3.42 3.42a15.995 15.995 0 0 0 4.764-4.648l3.876-5.814a1.151 1.151 0 0 0-1.597-1.597L14.146 6.32a15.996 15.996 0 0 0-4.649 4.763m3.42 3.42a6.776 6.776 0 0 0-3.42-3.42"
            />
        </svg>
    </button>
</div>

<style>
</style>
