<template>
  <div class="hello">
   <div v-for="(ele, index) in users" :key="index">{{ele.name}}</div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      users: []
    }
  },
  mounted(){
    axios.get('http://localhost:3003/api/users').then(res => {
      this.users = res.data
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
