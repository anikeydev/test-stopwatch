<template>
    <div class="stopwatch">
        <div class="time">
            <p class="time-text">21:30</p>
        </div>
        <div class="buttons">
            <button class="btn btn-play">
                <svg class="icon-play" width="17" height="20" viewBox="0 0 17 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path class="icon-play" d="M0 20V0L17 10L0 20Z" fill="#fff"/>
                </svg>
            </button>
            <button class="btn btn-stop">
                <svg class="icon-stop" width="20" height="20" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                    <rect class="icon-stop" width="20" height="20" fill="white"/>
                </svg>
            </button>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.stopwatch {
    height: 120px;
    width: 225px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin-bottom: 45px;

    background-color: #696969;
}

.time {
    width: 100%;
    height: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border-bottom: 1px solid #fff;
}

.time-text {
    color: #fff;
    line-height: 1;
    font-size: 22px;
}

.buttons {
    width: 100%;
    height: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.btn {
    margin: 0 25px;
    background: transparent;
    border: none;
    outline: none;
}

.btn-stop {
    width: 20px;
    height: 20px;
}

.btn-play {
    height: 20px;
}

.icon-stop {
    fill: #fff;
}

.icon-play {
    fill: #fff;
}
</style>