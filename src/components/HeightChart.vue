<template>
    <div id="height-table">
        <table>
            <tbody>
            <tr v-for="i in reversedItems" :key="i">
                <td>
                    {{i.toString() + "m"}}
                </td>
            </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        name: "height-chart",
        props: {
            meters: {
                type: Array
            }
        },
        computed: {
            reversedItems() {
                var max = this.meters.length;
                var arr = [];

                for(var i = max; i >= 0; i--){
                    arr.push(i)
                }

                return arr;
            }
        }
    }
</script>

<style scoped>
    table, th, td {
        border: none;
        border-collapse:separate;
        border-spacing:0 70px;
        color: white;
    }

</style>