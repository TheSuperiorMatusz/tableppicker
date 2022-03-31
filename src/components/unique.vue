<template>
  <div id="flex">
    <table>
      <thead>
        <tr>
          <th>id</th>
          <th>kolumna1</th>
          <th> kolumn2</th>
          <th>kolumna3</th>
          <th>kolumn4</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="column in columns" :key="column.id">
          <td>{{column.id}}</td>
          <td>{{column.kolumna1}}</td>
          <td>{{column.kolumna2}}</td>
          <td>{{column.kolumna3}}</td>
          <td>{{column.kolumna4}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "unique",
  data(){
    return{
      columns:[]
    };
  },
  async created(){
    try{
      const res= await axios.get('http://localhost:8080/api/tabela/unique');
      this.columns=res.data;
    }catch (e){
      console.error(e);
    }
  }
}
</script>

<style scoped>
table, th, td {
  border: 1px solid;
}
#flex{
  display: flex;
  justify-content: center;
}
</style>