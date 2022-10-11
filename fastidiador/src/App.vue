<template>
  <Cabecera></Cabecera>
  <Lista/>
</template>

<script>
import Cabecera from './components/Cabecera.vue'
import Lista from './components/Lista.vue'

export default {
  name: 'App',
  components: {
    Cabecera,
    Lista
  }
}
</script>

