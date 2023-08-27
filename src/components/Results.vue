<template>
    <div>
        <p >Reaction Time: {{ score }} ms</p>
        <p class="rank">{{ rank }}</p>
    </div>
</template>

<script>
export default {
    props:[ 'score' ],
    data(){
        return{
            rank: null,
        }
    },
    mounted(){
        if (this.score < 250){
            this.rank = 'Fingers';
        }else if (this.score < 400){
            this.rank = 'Reflexes';
        }else {
            this.rank = ' pace...'
        }
    }

}
</script>

<style>
.rank{
    font-size: 1.4em;
    color: aquamarine;
    font-weight: bold;
}
</style>