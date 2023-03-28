<template>
    <div 
        class="stopwatch"
        v-bind:class="{active: stopWatch.isActive}"
    >
        <div class="time">
            <p class="time-text">{{ time }}</p>
        </div>
        <div class="buttons">
            <PlayBtn 
                v-if="isPause" v-on:click="play"
                v-bind:isActive="isActive"
            />
            <PauseBtn v-else v-on:click="pause"/>
            <StopBtn
                v-on:click="reset"
                v-bind:isActive="isActive"
            />
        </div>
    </div>
</template>

<script>
import PlayBtn from './buttons/PlayBtn.vue'
import PauseBtn from './buttons/PauseBtn.vue'
import StopBtn from './buttons/StopBtn.vue'

export default {
    name: 'StopWatch',
    props: {
        stopWatch: {
            type: Object,
            required: true
        },
        stepms: Number
    },
    components: {
        PlayBtn,
        PauseBtn,
        StopBtn
    },
    data() {
        return {
            timer: null,
            isPause: true,
            sec: 0,
            min: 0,
            hour: 0,
        }
    },
    computed: {
        time() {
            if (!this.hour && !this.min && !this.sec) {
                return this.sec < 10 ? `0${this.sec}` : `${this.sec}`
            }
            if(this.sec > 0 && this.min === 0 && this.hour === 0) {
                return this.sec < 10 ? `0${this.sec}` : `${this.sec}`
            }
            if(this.min > 0 && this.sec >= 0 && this.hour === 0) {
                const minText = this.min < 10 ? `0${this.min}` : `${this.min}`
                const secText = this.sec < 10 ? `0${this.sec}` : `${this.sec}`
                return `${minText}:${secText}`
            }
            if(this.hour > 0 && this.sec >= 0 && this.min >= 0) {
                const hourText = this.hour < 10 ? `0${this.hour}` : `${this.hour}`
                const minText = this.min < 10 ? `0${this.min}` : `${this.min}`
                const secText = this.sec < 10 ? `0${this.sec}` : `${this.sec}`
                return `${hourText}:${minText}:${secText}`
            }
            
        }
    },
    methods: {
        tick() {
            this.sec += 1
            if(this.sec >= 60) {
                this.sec = 0
                this.min += 1
                if(this.min >= 60) {
                    this.min = 0
                    this.hour += 1
                }
            }
            this.play()
        },
        play() {
            this.isPause = false
            this.stopWatch.isActive = true
            this.timer = setTimeout(this.tick, this.stepms || 1000)
        },

        pause() {
            this.isPause = true
            this.stopWatch.isActive = false
            clearTimeout(this.timer)
        },

        reset() {
            this.isPause = true
            this.stopWatch.isActive = false
            clearTimeout(this.timer)
            this.sec = 0
            this.min = 0
            this.hour = 0
        }
    }
}
</script>

<style>
.stopwatch {
    height: 120px;
    width: 225px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 0 25px 45px;

    background-color: #696969;
}

.active .time {
    color: #fff;
    border-bottom: 1px solid #fff;
}

.time {
    width: 100%;
    height: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #9e9e9e;
    border-bottom: 1px solid #9e9e9e;
}

.time-text {
    /* color: #9e9e9e; */
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
    cursor: pointer;
}
</style>