<template>
    <button 
        class="btn btn-stop"
        v-bind:class="{active: isActive}"
    >
        <svg class="icon-stop" width="20" height="20" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <rect class="icon-stop" width="20" height="20"/>
        </svg>
    </button>
</template>

<script>
export default {
    name: 'StopBtn',
    props: {
        isActive: Boolean
    }
}
</script>

<style scoped>
.btn-stop {
    width: 20px;
    height: 20px;
}

.active .icon-stop {
    fill: #fff;
}

.icon-stop {
    fill: #9e9e9e;
}
</style>