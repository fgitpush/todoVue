<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input v-model="something" @keydown.enter="submitTodo" type="text" name="todo" placeholder="Todo">
    <h2>{{ item }}</h2>
    <ul id="example-1">
      <li v-for="item in something" v-bind="something">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    return {
      item: 'null',
      something: []
    }
  },
  props: {
    msg: String,
  },
  methods:{
    submitTodo()
    {
      this.item=this.something
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
