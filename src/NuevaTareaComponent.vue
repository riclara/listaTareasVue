<template>
  <div class="input-group">
      <div class="input-group">
      <input type="text" class="form-control" v-model="nuevaTarea" v-on:keyup.enter="agregarTarea" placeholder="Escribe una nueva tarea">
      <span class="input-group-btn">
        <button v-on:click="agregarTarea" class="btn btn-primary" type="button">Agregar</button>
      </span>
    </div>

  </div>
</template>

<script>
export default {
    data(){
        return {
            nuevaTarea: ""
        }
    },
    props: ["tareas"],
    methods : {
        agregarTarea(){
            var texto = this.nuevaTarea.trim()
            if(texto){
                this.tareas.push({
                    texto: texto,
                    terminada: false
                })
            }
        }
    }
};
</script>

