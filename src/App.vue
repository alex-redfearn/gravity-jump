<template>
    <div class="universe">
        <astronaut v-bind:height="height"/>

        <height-chart v-bind:meters="Array(70)"/>

        <div class="planet">
            <planet-drop-down v-bind:planets="planets"/>
            <Jump/>
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
        comments: {
            HeightChart
        },
        data() {
            return {
                planets: [
                    {
                        id: 1,
                        name: "Mercury",
                        gravity: 3.7
                    },
                    {
                        id: 2,
                        name: "Jupiter",
                        gravity: 24.9
                    },
                    {
                        id: 3,
                        name: "Mars",
                        gravity: 3.7
                    }
                ],
                height: [
                    {
                        meters: 5
                    }
                ]
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
