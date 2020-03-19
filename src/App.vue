<template>
    <div>
        <height-chart v-bind:meters="Array(70)"/>
    </div>
</template>

<script>
    import HeightChart from "./components/HeightChart";

    export default {
        name: 'app',
        components: {HeightChart},
        comments: {
            HeightChart
        }
    }
</script>

<style>
body {
    background-color: black;
}

</style>
