<template>
    <div class="ma-3">
        <div class="ma-0">
            <div class="mx-3"></div>
            <div class="mr-3">
                <RouterLink to="/tool">操作指引</RouterLink> |
                <router-link to="/display">圖層總攬</router-link> |
                <router-link to="/setting">其他圖層需求</router-link>
            </div>
        </div>
        <div class="ma-0">
            <div class="mx-3">
                123
            </div>
            <div class="mr-3" style="height:600px">
                <img style="width: 100%; height: 100%;" :src="src">
            </div>
        </div> 
    </div> 
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
    .div{
        border: 1px black solid;
    }
</style>