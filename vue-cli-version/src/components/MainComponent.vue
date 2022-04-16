<template>
    <main>
        <div id="JumboTron-container">
            <JumboTronComponent />
            <SectionCaroselComponent />
        </div>
    </main>
</template>

<script>
import JumboTronComponent from '@/components/JumboTronComponent.vue';
import SectionCaroselComponent from '@/components/SectionCaroselComponent.vue';

export default {
    name:'MainComponent',
    components: {
        JumboTronComponent,
        SectionCaroselComponent,
    },
}
</script>

<style lang="scss" scoped>
@import '../style/general';

main{
    width: 100%;
    height: 1000px;
    border: 1px dashed blue;
    #JumboTron-container{
        width: 100%;
    }
}

</style>