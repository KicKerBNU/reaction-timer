<template>
    <div class="space"></div>
    <div>Your score is {{score}} ms</div>
    <h5 class="green-text"> {{rank}} </h5>
</template>

<script>
export default {
    props: {
        score: Number,
    },
    data() {
        return {
            rank: null
        }
    },
    mounted(){
        if(this.score < 250) {
            this.rank = "Fast"
        } else if (this.score < 400) {
            this.rank = 'Rapid'
        } else {
            this.rank = "Slow"
        }
    }
}
</script>

<style>

</style>