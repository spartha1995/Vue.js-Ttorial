<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <hr />
    <div>
      <ul>
        <li v-for="user in users">
          {{user.firstname}} {{user.lastname}}
        </li>
      </ul>
    </div>
    <hr />

    <div>
      <input type="text" v-model="input_val">
    </div>
    <div>
      Input Value: <span v-text="input_val"></span>
    </div>
    <hr />

    <div>
      <button class="btn btn-primary" v-on:click="counter++">You've clicked this button {{counter}} times!</button>
    </div>

    <div>
  <span v-bind:title="message">
    Hover your mouse over me for a few seconds
    to see my dynamically bound title!
  </span>
</div>

<div>
  <p v-if="seen">Now you see me</p>
</div>

<div>
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>

  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      message:'Reverse ',
      seen: true,
      
      users: [
        {firstname: 'partha', lastname: 'Sarkar'},
        {firstname: 'Sandipan', lastname: 'Ghosh'},
        {firstname: 'Harry', lastname: 'Poddar'}
      ],

      todos: [
      { text: 'Learn JavaScript' },
      { text: 'Learn Vue' },
      { text: 'Build something awesome' }
    ],

    methods:{
      method:function(){
        this.message.split('').reverse().join();
      } 
    },
      input_val: '',
      counter: 0
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: large;
}
ul {
    list-style-position: inside;
}
a {
  color: #42b973;
}
</style>