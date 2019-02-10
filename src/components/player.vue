<template>
    <div>
        <h3>{{ name }}</h3>
        <audio controls controlsList="nodownload">
            <!--<source ref="player" v-bind:src="file" type="audio/mpeg">-->
            <source src="../assets/tracks/5G.mp3">
        </audio>
    </div>
</template>

<script>
export default{
    name: "player",
    props: {
        name: {
            type: String,
            default: null
        },
        file:{
            type: String,
            default: null
        }
    },
    mounted: function () {
            this.$watch('file', function() {
                this.$refs.player.load()
            });
            console.log(this.$refs)
        }
}
</script>

<style scoped>

</style>
