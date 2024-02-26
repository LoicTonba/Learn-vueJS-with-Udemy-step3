<template>
    <div class="header-top">
        <p>{{ titre }}</p>
    </div>
</template>

<script>
import {bus} from '../main'
    export default {
        name: 'Hea_der',
        data(){
            return{
                titre: 'Mon titre de base'
            }
        },
        beforeCreate(){
            console.log('Il va etre crée !')
        },
        created(){
            console.log("Le composant est crée !")
            bus.$on('changeTitre', (data) => {
                this.titre = data
            })
        },
        beforeMount(){
            console.log("Il va etre monté dans le DOM ")
        },
        mounted(){
            console.log("Il est intégré dans le DOM")
        },
        beforeUpdate(){
            console.log("Il va se mettre à jour")
        },
        updated(){
            console.log("Le composant s'est mis à jour !")
        }
    }
</script>

<style scoped>
    .header-top {
        position: fixed;
        top: 0;
        height: 50px;
        background: #333;
        color:#f1f1f1;
        width: 100%;
        text-align: center;
        line-height: 50px;
        font-size: 25px;
    }
</style>
