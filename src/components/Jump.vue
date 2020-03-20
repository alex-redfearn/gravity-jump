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
                force: 4,
                gravity: 4
            }
        },
        mounted: function () {
            window.setInterval(() => {
                this.jump()
            }, 20)
        },
        props: {
            height: Array
        },
        methods: {
            jump() {
                const astronaut = document.getElementById("astronaut");
                const height = this.ground - (this.height[0].meters * 80);

                if (this.jumping === true && this.position >= height) {

                    this.position = this.position - this.gravitationalPull(this.position, height, this.force)
                    astronaut.style.top = this.position + "px"

                    if (this.position <= height) {
                        this.jumping = false
                    }
                }

                if (this.jumping === false && this.position <= this.ground - 1) {
                    this.position = this.position + this.gravitationalPull(this.position, height, this.gravity)
                    astronaut.style.top = this.position + "px"
                }

                if (this.jumping === false && this.position >= this.ground) {
                    this.reset = true
                } else if (this.reset === true) {
                    astronaut.style.top = this.ground + "px"
                    this.position = this.ground
                }
            },
            setJumping(reset) {
                this.reset = reset
                this.jumping = ((!reset))
            },
            gravitationalPull(position, height, velocity) {
                const difference = position - height;

                if (difference < 10) {
                    return velocity - 3
                } else if (difference > 10 && difference < 20) {
                    return velocity - 2
                } else if (difference > 20 && difference < 30) {
                    return velocity - 1
                } else {
                    return velocity
                }
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