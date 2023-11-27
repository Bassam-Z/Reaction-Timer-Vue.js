<template>
    <div class="block" v-if="showBlock" @click="stopTimer" >
        click me
    </div>
    <!-- <div v-if="showRactionTime">{{ ractionTime }}</div> -->
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return {
            showBlock: false,
            timer: null,
            ractionTime: 0,
            showRactionTime: false,
        }
    },
    methods:{
        strtTimer() {
            this.timer = setInterval(() => {
                this.ractionTime += 10;
            }, 10);
        },
        stopTimer() {
            clearInterval(this.timer);
            this.$emit('end', this.ractionTime);
            // this.ractionTime.
            // this.showRactionTime = true;

        }
    },
    mounted(){
        console.log('Compunent is mounted');
        setTimeout(() => {
            this.showBlock = true;
            this.strtTimer();
            console.log(this.delay)
        },this.delay)
    },
    updated() {
        console.log('component updated');
    },
    unmounted(){
        console.log('unmounted');
    }

}
</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>