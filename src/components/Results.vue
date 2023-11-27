<template>
    <p>Reaction Time: {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props:['score'],
    data() {
        return {
            rank: null
        }
    },
    mounted() {
        if (this.score < 250){
            this.rank = 'Sehr Gut';
        }else if (this.score < 400){
            this.rank = 'Gut';
        }else {
            this.rank = 'Ausreichend'
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