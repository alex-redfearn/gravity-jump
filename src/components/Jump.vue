<template>
    <div class="jump" v-if="jumping === true">
        <button v-on:click="jumping = false">
            Reset
        </button>
    </div>
    <div class="jump" v-else>
        <button v-on:click="jumping = true">
            Jump
        </button>
    </div>
</template>

<script>
    export default {
        name: "Jump",
        data() {
            return {
                jumping: true
            }
        },
        methods: {
            jump() {
                console.log("hello")
            }
        }
    }
</script>

<style>
    .jump {
        width: 100px;
        height: 30px;
        color: black;
        display: inline-block;
    }

</style>