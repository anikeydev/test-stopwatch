<template>
    <ul class="stopwatch-list">
        <StopWatch />
        <StopWatch />
        <StopWatch />
        <StopWatch />
    </ul>
</template>

<script>
import StopWatch from './StopWatch.vue'

export default {
    name: 'StopWatchList',
    components: {
        StopWatch
    }
}
</script>

<style>

.stopwatch-list {
    list-style: none;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    max-width: 775px;
    margin-top: 72px;
}

</style>