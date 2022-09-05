<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
    Click Me
  </div>
</template>

<script>
export default {
    props:["delay"],
    data() {
        return {
            showBlock:false,
            timer: null,
            actionTimer: 0,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay)
        console.log("component mounted");
    },
    methods:{
        startTimer() {
            this.timer = setInterval(() => {
                this.actionTimer += 10;
            }, 10)
        },
        stopTimer() {
            console.log(this.actionTimer);
            clearInterval(this.timer);
            this.$emit("end", this.actionTimer);
        }
    }
    // updated() {
    //     console.log("component updated")
    // },
    // unmounted() {
    //     console.log("component unmounted")
    // }
}
</script>

<style>
    .block{
        width:400px;
        margin: 40PX auto;
        padding: 100px 0;
        background: #0fa078;
        color: white;
        text-align: center;
        border-radius: 20px;
    }
</style>