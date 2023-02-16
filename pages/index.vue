<template>
  <h1 class="title">Welcome to the homepage</h1>
  <div class="home">
    <div class="content"></div>
    <div class="side">
      <Item :abstract="abstract"/>
      <Item :abstract="abstract2"/>
      <Item :abstract="abstract3"/>

    </div>
  </div>
</template>
  
  <script>
  import Item from '../components/Item.vue';
  export default {
    name: 'index',
    components: { Item },
    data () {
      return {
        abstract: 'Example abstract 1',
        abstract2: 'Example abstract 2',
        abstract3: 'Example abstract 3'
      }
    }
  }
</script>
  