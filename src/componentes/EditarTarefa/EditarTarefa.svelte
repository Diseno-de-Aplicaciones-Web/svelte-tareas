<script>
    
    export let tarefa

    let editando = false

    function manexadorEditar() {
        editando = true
    }

    function manexadorGardar() {

        const tarefaJSON = JSON.stringify(tarefa)

        fetch(
            "http://localhost:8000/tarefas/",
            {
                method: "PUT",
                headers: {
                    "Content-Type": "application/json"
                },
                body: tarefaJSON
            }
        )

        editando = false

    }

</script>

<div>
    <button on:click={manexadorEditar}>Editar</button>
    {#if (editando === true)}
    <label>
        Descripcion:
        <input type="text" bind:value={tarefa.descripcion}>
    </label>
    <label>
        Completada:
        <input type="checkbox" bind:checked={tarefa.completada}>
    </label>
    <button on:click={manexadorGardar}>Gardar</button>
    {/if}
</div>