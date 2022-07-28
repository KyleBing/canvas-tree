<template>
    <canvas ref="canvas"></canvas>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
    name: 'App',
    components: {
        HelloWorld
    },
    data(){
        return {
            height: 1000,
            width: 1000,

            context: null,
        }
    },
    mounted() {
        onresize = () => {
            this.height = innerHeight
            this.width = innerWidth
        }
        this.draw()

    },
    methods: {
        draw(){
            let context = this.$refs.canvas.getContext('2d')
            context.beginPath()
            context.moveTo(200,0)
            context.lineTo(200,200)
            context.arc(200,200, 100,Math.PI * 0,Math.PI * 0.5, false )
            context.closePath()
            context.stroke()
        }
    }
}
</script>

<style lang="scss">

</style>
