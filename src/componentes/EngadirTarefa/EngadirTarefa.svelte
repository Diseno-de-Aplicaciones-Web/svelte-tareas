<script>

    import ListaTarefas from "../ListaTarefas/ListaTarefas.svelte";

    let listaDeTarefas = []
    let descripcion = ""
    let completada = false

    $: novaTarefa = {
        id: Date.now(),
        descripcion: descripcion,
        completada: completada
    }
    
    function manexadorEngadir() {
        fetch(
            "http://localhost:8000/tarefas/",
            {
                method: "POST",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify(novaTarefa)
            }
        ).then(

        )
    }

    function manexadorActualizar() {
        fetch("http://localhost:8000/tarefas/").then(
            resposta => resposta.json().then(
                datos => listaDeTarefas = datos
            )
        )
    }

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

    <button on:click={manexadorEngadir}>Engadir tarefa</button>
    <button on:click={manexadorActualizar}>Actualizar</button>

</fieldset>

<ListaTarefas propiedadeListaTarefas={listaDeTarefas}/>
