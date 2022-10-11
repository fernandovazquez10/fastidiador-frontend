<template>
    <div>
        <ul class="list-group">
            <li v-for="(item, index) of array_ordenado" :key="item.nombre" @click="aumentar(index)"
            class="list-group-item d-flex justify-content-between align-items-center">
                {{index}} - {{item.nombre}}
                <span class="badge badge-primary badge-pill">{{item.cantidad}}</span>
            </li>
            <button class="btn btn-danger bnt-block" @click="reiniciar">Reiniciar</button>
        </ul>
    </div>
</template>

<script>
import {mapState, mapMutations} from 'vuex';

export default{
    name: 'Lista',
    computed: {
        ...mapState(['frutas']), 
        array_ordenado(){
            return this.frutas.sort((a, b) => b.cantidad - a.cantidad)
        }
    },
    methods:{
        ...mapMutations(['aumentar', 'reiniciar'])
    }
}
</script>
