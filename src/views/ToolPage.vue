<template>
    <v-row class="ma-3">
        <v-col class="mx-3" md="4">
            123
        </v-col>
        <v-col class="mr-3" style="height:600px">
            <img style="width: 100%; height: 100%;" :src="src">
        </v-col>
    </v-row>  
</template>

<script>

    export default {
        data(){
            return{
                src: require('../images/map.jpg')
            }
        }
        
    }
</script>

<style lang="scss" scoped>
    .v-col{
        border: 1px black solid;
    }
</style>