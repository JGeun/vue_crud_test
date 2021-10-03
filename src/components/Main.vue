<template>
  <div>
    <Clocks :style="{'position':'absolute'}"/>
    <Todos :style="{'position':'absolute'}"/>
  </div>
</template>

<script>
  import Clocks from './Clock.vue';
  import Todos from './Todo.vue';

  export default {
    components: {
      Clocks, Todos
    },
  }
</script>
