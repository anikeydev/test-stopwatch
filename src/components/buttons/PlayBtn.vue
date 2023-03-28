<template>
    <button class="btn btn-play" v-bind:class="{ active: isActive }">
        <svg class="icon-play" width="17" height="20" viewBox="0 0 17 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path class="icon-play" d="M0 20V0L17 10L0 20Z" fill="#fff" />
        </svg>
    </button>
</template>

<script>
export default {
    name: 'PlayBtn',
    props: {
        isActive: Boolean
    }
}
</script>

<style scoped>
.btn-play {
    height: 20px;
}

.active .icon-play {
    fill: #fff
}

.icon-play {
    fill: #9e9e9e;
}
</style>