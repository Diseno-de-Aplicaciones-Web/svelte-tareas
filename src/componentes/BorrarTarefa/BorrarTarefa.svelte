<button on:click={manexadorBorrar}>x</button>

<script>

    export let tarefa

    function manexadorBorrar() {
        const tarefaJSON = JSON.stringify({ id: tarefa.id })
        const promesaResposta = fetch(
            "http://localhost:8000/tarefas/",
            {
                method: "DELETE",
                headers: {
                    "Content-Type": "application/json"
                },
                body: tarefaJSON
            }
        )
    }

</script>