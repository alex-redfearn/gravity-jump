<template>
    <div>
        <select id="planets">
            <option v-for="planet in planets" :key="planet.id" :value="planet.id">
                {{planet.name}}
            </option>
        </select>
    </div>
</template>

<script>
    export default {
        name: "planet-drop-down",
        props: {
            planets: Array
        }
    }
</script>

<style scoped>

</style>