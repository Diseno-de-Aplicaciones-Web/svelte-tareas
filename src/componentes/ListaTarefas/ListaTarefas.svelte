<script>

    import Tarefa from "../Tarefa/Tarefa.svelte";
    import BorrarTarefa from "../BorrarTarefa/BorrarTarefa.svelte";
    import EditarTarefa from "../EditarTarefa/EditarTarefa.svelte";

    export let propiedadeListaTarefas // Propiedade <ListaTarefas propiedadeListaTarefas=""/>

</script>

<ol>
    {#each propiedadeListaTarefas as cadaTarefa}
    <li>
        <Tarefa propiedadeTarefa={cadaTarefa}/>
        <BorrarTarefa tarefa={cadaTarefa}/>
        <EditarTarefa bind:tarefa={cadaTarefa}/>
    </li>
    {/each}
</ol>