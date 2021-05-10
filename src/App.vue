<template>
  <h1 class="text-3xl font-bold text-center mt-20">Prova nr 1</h1>
  <pre>{{dati}}</pre>

</template>
 
<script >
import {defineAsyncComponent } from 'vue'
//import dInput from "@comp/dinput.vue";
const dInput = defineAsyncComponent(() => import('@comp/dinput.vue'))
export default {
  components: { dInput },
  data() {
    return {
      dati:[],
    };
  },
  created() {
    var tm=this
    fetch('https://jsonplaceholder.typicode.com/users')
    .then(res => res.json())
    .then(res => tm.dati=res)
  }


};
</script>
