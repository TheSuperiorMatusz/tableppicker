<template>
  <div>
    <select @change="selectCategory($event)">
      <option>--SELECT--</option>
      <option value="unique">Unique</option>
      <option value="notunique">Notunique</option>
    </select>
  </div>
  <div v-if="this.value==='unique'">
    <unique/>
  </div>
  <div v-else-if="this.value==='notunique'">
    <notunique/>
  </div>
  <div v-else>
    <h1>Wybierz </h1>
  </div>
</template>

<script>
import Unique from "@/components/unique";
import Notunique from "@/components/notunique";

export default {
  name: 'App',
  components: {
    Notunique,
    Unique
  },
  data(){
    return{
      value:null
    }
  },
  methods:{
    selectCategory(event){
      console.log(event.target.value);
      this.value=event.target.value;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
