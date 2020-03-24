<template>
    <div class="planetDropDown">
        <select id="planets" @change="planetChanged($event)">
            <option v-for="planet in planets" :key="planet.id" :value="planet.name">
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
        },
        methods: {
            planetChanged(event) {
                const planet = event.target.value;
                this.$emit('planetChanged', planet)
            }
        }
    }
</script>

<style>
    .planetDropDown {
        display: inline-block;
    }

</style>