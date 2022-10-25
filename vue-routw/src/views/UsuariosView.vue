<template>
    <div>
        <h1> Lista de usuario</h1>

        <router-link :to="{name: 'usuario', params:{id: item}}" 
        v-for="(item, index) of listausuarios" :key="index">
            <button>foto {{item}}</button>
        </router-link>
    </div>
    <usuario />
    <button @click="home">Home</button>
    <button @click="anterior">Anterior</button>
    <button @click="siguiente">Siguiente</button>
</template>

<script>
import usuario from "@/components/Usuario.vue"

export default{
    name: 'ususarios',
    components: {
        usuario
    },
    data(){
        return{
            listausuarios: [1,2,3,4,5]
        }
    },
    methods:{
        home(){
            this.$router.push('/')
        },
        anterior(){
            this.$router.go(-1)
        },
        siguiente(){
            this.$router.go(1)
        }
    }
}
</script>
