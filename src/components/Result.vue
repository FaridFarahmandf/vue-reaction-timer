<template>
  <p>reaction timer: {{ timelaps }}</p>
  <p class="rank">Your rank is - {{rank}}</p>
</template>

<script>
export default {
    props: ["timelaps"],
    data(){
        return {
            rank:"",
        }
    },
    mounted(){
        if(this.timelaps < 250){
            this.rank = "Wow Are you Sonic !?"
        }else if(this.timelaps < 450){
            this.rank = "norm of speed";
        }else {
            this.rank = "too slow"
        }
    },
}
</script>

<style>
.rank {
    box-shadow: 1px 1px 10px #0fa078;
    padding: 10px;
    width: 400px;
    margin: 20px auto;
    color: #fff;
    background-color: #0fa078;
    border-radius: 20px;
}
</style>