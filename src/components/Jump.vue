<template>
    <div class="jump">
        <button v-on:click="jump()">
            JUMP
        </button>
    </div>
</template>

<script>
    export default {
        name: "Jump",
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