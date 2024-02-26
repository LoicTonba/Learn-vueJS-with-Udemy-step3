<template>
  <div class="container mt-5">

  <h1>{{ titre }}</h1>

    <div class="btn btn-outline-primary mr-2" v-on:click="component = 'texte1'">Onglet 1</div>
    <div class="btn btn-outline-primary" v-on:click="component = 'texte2'">Onglet 2</div>

    <div class="onglets card mb-5 mt-3" >
      <component class="p-5" v-bind:is="component"></component>
    </div>
   
  

  </div>
</template>

<script>
import Texte1 from './Texte1.vue';
import Texte2 from './Texte2.vue';
export default {
  name: 'HContenu',
  data: function(){
    return {
      myArr : [
        {titre: 'Inception', date: 2010},
        {titre: 'Avatar', date: 2009},
        {titre: 'Seven', date: 1995}
      ],
      txt: 'Hello World',
      titre: 'Je suis le Titre',
      toggle1:true,
      toggle2:false,
      component: 'texte1'
    }
  },
 methods: {
    toggleOng1: function(){
      this.toggle1 = true,
      this.toggle2 = false
    },
    toggleOng2: function(){
      this.toggle1 = false,
      this.toggle2 = true
    },
 },
  components: {
    'texte1':Texte1,
    'texte2':Texte2
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1{
    margin-top: 100px!important;
  }
  .onglets{
    height: 300px;
  }
</style>
