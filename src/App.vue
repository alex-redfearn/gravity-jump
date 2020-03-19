<template>
    <div class="universe">
        <div>
            <height-chart v-bind:meters="Array(70)"/>
        </div>
        <div class="planet">
            <div class="planetDropDown">
                <planet-drop-down v-bind:planets="planets"/>
            </div>
        </div>
    </div>
</template>

<script>
    import HeightChart from "./components/HeightChart";
    import PlanetDropDown from "./components/PlanetDropDown";

    export default {
        name: 'app',
        components: {
            HeightChart,
            PlanetDropDown
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
        border-radius: 50%;
        text-align: center;
        line-height: 150px;
        bottom: -50px;
        position: absolute;
    }

    .planetDropDown {
        display: inline-block;
        vertical-align: middle;
        line-height: normal;
    }

</style>
