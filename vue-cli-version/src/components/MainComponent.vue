<template>
    <main>
        <div id="JumboTron-container">
            <JumboTronComponent />
        </div>
        <div id="section-carosel">
            <SectionCaroselComponent />
        </div>
        <div id="search-component">
            <SectionFinderComponent/>
        </div>
    </main>
</template>

<script>
import JumboTronComponent from './MainsComponent/JumboTronComponent.vue';
import SectionCaroselComponent from './MainsComponent/SectionCaroselComponent.vue';
import SectionFinderComponent from './MainsComponent/SectionFinderComponent.vue';

export default {
    name:'MainComponent',
    components: {
        JumboTronComponent,
        SectionCaroselComponent,
        SectionFinderComponent
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