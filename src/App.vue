<template>
  <StopWatchList 
    v-bind:stopWatchesArr="stopWatchesArr" 
    v-bind:stepms="stepms" 
    v-on:add-stopwatch="addStopWatch" 
  />
</template>

<script>
import StopWatchList from './components/StopWatchList.vue'

export default {
  name: 'App',
  components: {
    StopWatchList
  },
  data() {
    return {
      stepms: 1000, // this is tick of ms, for faster visual tetsing
      stopWatchesArr: [
        { id: 1, isActive: false },
        { id: 2, isActive: false },
        { id: 3, isActive: false }
      ]
    }
  },
  methods: {
    addStopWatch() {
      const newStopWatch = {
        id: Date.now
      }
      this.stopWatchesArr.push(newStopWatch)
    }
  }
}

</script>

<style>
body {
  font-family: 'Gotham Pro';
  font-weight: 400;

  background-color: #353638;
}

#app {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
}
</style>
