<template>
    <div class="button" v-if="reset === true">
        <button v-on:click="setJumping(false)">
            Jump
        </button>
    </div>
    <div class="button" v-else>
        <button v-on:click="setJumping(true)">
            Reset
        </button>
    </div>
</template>

<script>
    export default {
        name: "Jump",
        data() {
            return {
                greeting: "hello",
                jumping: false,
                reset: true,
                position: 6270,
                ground: 6270,
                upwardVelocity: 1,
                gravity: 1
            }
        },
        mounted: function () {
            window.setInterval(() => {
                this.jump()
            }, 10)
        },
        props: {
            height: Array
        },
        methods: {
            jump() {
                var astronaut = document.getElementById("astronaut")
                var height = this.ground - (this.height[0].meters * 90)

                if (this.jumping === true && this.position >= height) {

                    this.position = this.position - this.upwardVelocity
                    astronaut.style.top = this.position + "px"

                    if (this.position <= height) {
                        this.jumping = false

                    }
                }

                if (this.jumping === false && this.position <= this.ground - 1) {
                    this.position = this.position + this.gravity
                    astronaut.style.top = this.position + "px"
                }

                if (this.jumping === false && this.position === this.ground) {
                    this.reset = true
                } else if(this.reset === true) {
                    astronaut.style.top = this.ground + "px"
                    this.position = this.ground
                }
            },
            setJumping(reset) {
                this.reset = reset
                this.jumping = ((!reset))
            }
        }
    }
</script>

<style>
    .button {
        width: 100px;
        height: 30px;
        color: black;
        display: inline-block;
    }

</style>