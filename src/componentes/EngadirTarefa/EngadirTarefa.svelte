<script>

    import ListaTarefas from "../ListaTarefas/ListaTarefas.svelte";

    let listaDeTarefas = []
    let descripcion = ""
    let completada = false

    $: novaTarefa = {
        descripcion: descripcion,
        completada: completada
    }
    
    function manexadorClick() {
        listaDeTarefas.push(novaTarefa)
        listaDeTarefas = listaDeTarefas // Necesitamos empregar unha asignación
    }                                    // para que Svelte reaccione ó cambio do array.

</script>

<fieldset>

    <legend>
        Nova tarefa
    </legend>

    <label>
        <span>Descripcion:</span> <input type="text" bind:value={descripcion}/>
    </label>

    <label>
        <span>Completada:</span> <input type="checkbox" bind:checked={completada}/>
    </label>

    <button on:click={manexadorClick}>Engadir tarefa</button>

</fieldset>

<ListaTarefas propiedadeListaTarefas={listaDeTarefas}/>
