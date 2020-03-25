<template>
    <div class="universe">
        <astronaut id="astronaut"/>

        <height-chart/>

        <div class="planet">
            <planet-drop-down v-bind:planets="planets" @planetChanged="getHeight($event)"/>
            <Jump v-bind:height="height"/>
        </div>
    </div>
</template>

<script>
    import HeightChart from "./components/HeightChart";
    import PlanetDropDown from "./components/PlanetDropDown";
    import Astronaut from "./components/Astronaut";
    import Jump from "./components/Jump";

    export default {
        name: 'app',
        components: {
            HeightChart,
            PlanetDropDown,
            Astronaut,
            Jump
        },
        mounted() {
            this.getPlanets()
        },
        data() {
            return {
                planets: [],
                height:
                    {
                        meters: 0.5
                    }
            }
        },
        methods: {
            async getPlanets() {
                try {
                    const response = await fetch(`http://localhost:8081/planet`)
                    const data = await response.json()
                    this.planets = data
                } catch (error) {
                    console.log(error)
                }
            },
            async getHeight(planet) {
                try {
                    const response = await fetch(`http://localhost:8081/jump/${planet}`)
                    const data = await response.json()
                    this.height = data
                } catch (error) {
                    console.log(error)
                }
            }
        }
    }
</script>

<style>
    body {
        background-color: black;
    }

    .universe {
        position: relative;
    }

    .planet {
        width: 100%;
        height: 175px;
        background: mediumpurple;
        border-radius: 50% 50% 0% 0%;
        text-align: center;
        line-height: 175px;
        bottom: -50px;
        position: absolute;
    }
</style>
