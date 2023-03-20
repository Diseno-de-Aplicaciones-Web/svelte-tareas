<script>

    import Tarefa from "../Tarefa/Tarefa.svelte";

    export let propiedadeListaTarefas // Propiedade <ListaTarefas propiedadeListaTarefas=""/>

</script>

<ol>
    {#each propiedadeListaTarefas as cadaTarefa}
    <li><Tarefa propiedadeTarefa={cadaTarefa}/></li>
    {/each}
</ol>