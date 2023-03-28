<script>

    import Tarefa from "../Tarefa/Tarefa.svelte";
    import BorrarTarefa from "../BorrarTarefa/BorrarTarefa.svelte";

    export let propiedadeListaTarefas // Propiedade <ListaTarefas propiedadeListaTarefas=""/>

</script>

<ol>
    {#each propiedadeListaTarefas as cadaTarefa}
    <li>
        <Tarefa propiedadeTarefa={cadaTarefa}/>
        <BorrarTarefa tarefa={cadaTarefa}/>
    </li>
    {/each}
</ol>