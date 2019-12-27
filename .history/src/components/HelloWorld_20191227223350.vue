<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input v-model="something" @keydown.enter="submitTodo" type="text" placeholder="Enter Todo">
    <ul>
      <li v-for="(item, i) in todos" :key="i" style="display:block">
      <table>
        <tr>
            <td style="display:inline-block;"><span id="item">{{ item.todo }}</span></td>
            
        </tr>
      </table>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    return {
      something:"",
      todos: []
    }
  },
  props: {
    msg: String,
  },
  methods:{
    init(){
      this.loadTodo()
    },
    submitTodo()
    {
      localStorage.setItem(this.something, this.something);
      this.todos.push({ todo: this.something});
      this.something = ''
    },
    loadTodo()
    {
      for (var i = 0; i < localStorage.length; i++){
         this.todos.push({ todo: localStorage[i]});
         
      }
    }
  },
   mounted(){
    this.init()
  }
}
</script>

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
