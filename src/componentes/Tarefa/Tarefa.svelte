<script>

    export let propiedadeTarefa // Propiedade <Tarefa propiedadeTarefa=""/>

</script>

<label>
    <span>{propiedadeTarefa.descripcion}</span>
    <input type="checkbox" checked={propiedadeTarefa.completada}/>
</label>
