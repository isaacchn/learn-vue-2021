<template>
  <div id="app">{{ msg }}
    <div>
      <!--v-model双向绑定-->
      <input type="text" v-model="info">
      <button v-on:click="handleClick">添加</button>
    </div>
    <ul>
      <todo-item v-for="it in list" v-bind:key="it">
        <template v-slot:it_slot="it_prop">
          <span v-bind:style="{fontSize:'20px',color:it_prop.is_checked?'red':'blue'}">{{ it }}</span>
        </template>
      </todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'App',
  data() {
    return {
      msg: 'hello geektime',
      info: '',
      list: []
    }
  },
  methods: {
    handleClick() {
      console.log(this.info),
          this.list.push(this.info),
          this.info = ''
    }
  },
  components: {
    TodoItem
  }
}
</script>

<style>

</style>
