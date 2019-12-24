<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input v-model="something" @keydown.enter="submitTodo" type="text" placeholder="Enter Todo">
    <ul>
      <li v-for="(item, i) in todos" :key="i" style="display:block">
          <span id="item"> {{ item.todo }}</span>
          <span id="item"> {{ item.completed }}</span>
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
    submitTodo()
    {
      this.todos.push({ todo: this.something, completed: false });
      this.something = ''
    }
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
