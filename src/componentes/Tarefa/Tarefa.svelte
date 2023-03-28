<script>

    export let propiedadeTarefa // Propiedade <Tarefa propiedadeTarefa=""/>

    let estado = "ver"

    let inputHTML

    function manexadorEditar() {
        estado = "editar"
    }

    function manexadorGardar() {
        const tarefaJSON = JSON.stringify(propiedadeTarefa)
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
        inputHTML.blur()
        estado = "ver"
    }

</script>

<label>
    <input bind:this={inputHTML} type="text" class={estado}
        bind:value={propiedadeTarefa.descripcion}
        on:focus={manexadorEditar}
        on:blur={manexadorGardar}
    />
    {#if estado === "editar"}
    <button>Guardar</button>
    {/if}
    <input type="checkbox"
        bind:checked={propiedadeTarefa.completada}
        on:input={manexadorGardar}
    />

</label>


<style>
    .ver {
        border-style: none;
    }
    .editar {
        background-color: greenyellow;
    }
</style>