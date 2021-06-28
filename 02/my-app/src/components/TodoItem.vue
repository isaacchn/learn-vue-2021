<template>
  <li class="item_class">
    <input type="checkbox" v-model="is_checked">
    <slot name="it_slot" v-bind="{is_checked}"></slot>
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: ['it_prop'],
  data() {
    return {
      is_checked: false
    }
  }
}
</script>

<style scoped>
.item_class {
  color: red;
}
</style>