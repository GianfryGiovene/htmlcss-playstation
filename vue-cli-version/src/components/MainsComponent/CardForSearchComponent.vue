<template>
    <div class="ggf-card" >
        <div>
            <img :src="getElementsToSearch.img" alt="">
            <span>{{ getElementsToSearch.title }}</span>
        </div>
    </div>
</template>
    
<script>

export default {
    name:'CardForSearchComponent',
    props:{
        getElementsToSearch: Object,
    }

}
</script>

<style lang="scss" scoped>
    .ggf-card{
        width: calc(100% / 6 - 1rem);
        margin: 5px;
        &> div{
            width: 100%;
            
            img{
                width: 100%;
            }
        }
    }
</style>