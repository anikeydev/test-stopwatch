<template>
    <div class="stopwatch-add">
        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect x="8.5" width="3" height="20" fill="#fff"/>
            <rect y="11.5" width="3" height="20" transform="rotate(-90 0 11.5)" fill="#fff"/>
        </svg>
    </div>
</template>

<script>
export default {
    name: 'AddStopWatch'
}
</script>

<style>
.stopwatch-add {
    display: flex;
    align-self: start;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    height: 120px;
    width: 225px;
    margin: 0 25px 45px;

    background-color: #696969;
    cursor: pointer
}
</style>