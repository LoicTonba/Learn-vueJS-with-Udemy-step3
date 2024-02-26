<template>
    <div>
      <ul class="liste mt-5">
        <li v-for="(film, index) in myArr" v-bind:key="index">
          <div class="card">
            <div class="card-body">
              Titre: {{ film.titre }}
              <br>
              Date: {{ film.date }}
            </div>
          </div>
        </li>
     </ul>
     <p>{{ txt }}</p>
    <div v-on:click="supprFilm" class="btn btn-danger mt-2">Supprime le film</div>
    <div  class="btn btn-danger mt-2 ml-2">Supprime le text</div>
    <div  v-on:click="changeTitre" class="btn btn-danger mt-2 ml-2">Modifie le titre</div>

    <slot>Patientez</slot>
    <slot name="info"></slot>
  </div>    
</template>

<script>
import {bus} from '../../main'
export default {
  name: 'Lis_te',
  data: function(){
    return{
        fruits: ['Orange', 'Papaye', 'Fraise']
    }
  },
  methods: {
    changeTitre: function(){
      //this.$emit('changeTitre','Mon nouveau titre')
      bus.$emit('changeTitre','Titre changé avec le bus!')
    }
    
  },
  props: ['myArr','txt']
}

</script>

<style scoped src="./Liste.css">


</style>

