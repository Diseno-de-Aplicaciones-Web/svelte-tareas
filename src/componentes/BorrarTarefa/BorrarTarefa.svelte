<button on:click={manexadorBorrar}>x</button>

<script>

    export let tarefa

    function manexadorBorrar() {
        const promesaResposta = fetch(
            "http://localhost:8000/tarefas/",
            {
                method: "DELETE",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify({ id: tarefa })
            }
        )
    }

</script>