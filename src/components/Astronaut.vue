<template>
    <div>
        <img class="astronaut" alt="Vue logo" src="./../assets/astronaut.jpg">
    </div>
</template>

<script>
    export default {
        name: "astronaut"
    }
</script>

<style>
    .astronaut {
        width: 50px;
        height: 60px;
        position: absolute;
        z-index: 99;
        left: 48%;
        top: 98%;
    }

</style>