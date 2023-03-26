<template>
  <div id="app">
    <StopWatchList />
  </div>
</template>

<script>
import StopWatchList from './components/StopWatchList.vue'

export default {
  name: 'App',
  components: {
    StopWatchList
  }
}

</script>

<style>
body {
  background-color: #353638;
  font-family: 'Gotham Pro';
  font-weight: 400;
}

#app {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
}
</style>
