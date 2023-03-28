<template>
    <ul class="stopwatch-list">
        <StopWatch 
            v-for="stopWatch of stopWatchesArr"
            v-bind:stopWatch="stopWatch"
            v-bind:stepms="stepms"
        />
        <AddStopWatch v-on:click="$emit('add-stopwatch')"/>
    </ul>
</template>

<script>
import StopWatch from './StopWatch.vue'
import AddStopWatch from './AddStopWatch.vue'

export default {
    name: 'StopWatchList',
    components: {
        StopWatch,
        AddStopWatch
    },
    props: {
        stopWatchesArr: {
            type: Array,
            required: true
        },
        stepms: Number
    }
}
</script>

<style>
.stopwatch-list {
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    max-width: 825px;
    margin-top: 72px;
}

@media(min-width: 825px) {
    .stopwatch-list {
        justify-content: start;
    }
}
</style>