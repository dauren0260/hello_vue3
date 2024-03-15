<script lang="ts">
import Person from './components/Person.vue';

export default {
  name: 'App',
  components: {Person}
}
</script>

<template>
  <header>
    <div class="wrapper">
      <Person />
    </div>
  </header>

</template>

<style scoped>
.wrapper{
  background-color: #ffa454;
  padding: 20px;
}
</style>
