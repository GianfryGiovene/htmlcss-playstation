<template>
    <section>
        <div>
            <div>
                <SearchComponent @search="wordToFind"/>
            </div>
            <div>
                <CardForSearchComponent :key="index" v-for="(item,index) in filterArray" :getElementsToSearch="item" />
            </div>
        </div>
    </section>
</template>

<script>
import SearchComponent from '@/components/MainsComponent/SearchComponent.vue';
import CardForSearchComponent from '@/components/MainsComponent/CardForSearchComponent.vue';
import TonyHowks from '@/assets/tony-hawks-pro-skater-1-2-store-art.jpg';
import CrashBandicoot from '@/assets/crash-bandicoot.jpg'

export default {
    name:'SectionFinderComponent',
    components:{
        SearchComponent,
        CardForSearchComponent,
    },
    data(){
        return{
            SearchComponentsElements:[
                {   
                    indice: 0,
                    img: TonyHowks,
                    title:'Tony Hawks Pro Skater'
                },
                {
                    indice: 1,
                    img: CrashBandicoot,
                    title:'Crash Bandicoot'
                },
                {
                    indice: 2,
                    img: TonyHowks,
                    title:'Pino robot'
                },
                {
                    indice: 3,
                    img: CrashBandicoot,
                    title:'Ernesto fasulo'
                },
                {
                    indice: 4,
                    img: TonyHowks,
                    title:'Pirino Marasciuolo'
                },
                {
                    indice: 5,
                    img: CrashBandicoot,
                    title:'Perlato di sera'
                },
                {
                    indice: 6,
                    img: TonyHowks,
                    title:'Pino robot1'
                },
                {
                    indice: 7,
                    img: CrashBandicoot,
                    title:'Ernesto fasulo1'
                },
                {
                    indice: 8,
                    img: TonyHowks,
                    title:'Pirino Marasciuolo1'
                },
                {
                    indice: 9,
                    img: CrashBandicoot,
                    title:'Perlato di sera1'
                },
                {
                    indice: 10,
                    img: TonyHowks,
                    title:'Pirino Marasciuolo2'
                },
                {
                    indice: 11,
                    img: CrashBandicoot,
                    title:'Perlato di sera2'
                }
            ],
            wordSearched:'',
        }
    },
    methods:{
        // salvo in un dato l'emit che arriva dal SearchComponent
        wordToFind(wordToSearch){
            this.wordSearched = wordToSearch;
        }
        
    },
    computed:{
        // genera 'SearchComponentsElements' dinamicamente
        filterArray(){
            let filteredByInput = this.SearchComponentsElements;
            if(this.wordSearched !==''){
                return filteredByInput.filter(item=> item.title.toLowerCase().includes(this.wordSearched.toLowerCase())); 
            }
            return filteredByInput;
        }
    },
}
</script>

<style lang="scss" scoped>
@import '@/style/general';
    section{
        width: 100%;
        color: $white;
        background-color: $bg-grey;
        & > div{
            padding-top: 50px;
            max-width: 1200px;
            margin: auto;
            & > div:first-child{
                padding-bottom: 20px;
            }
            & > div:last-child{
                display: flex;
                justify-content: center;
                align-items: center;
                flex-wrap: wrap;
            }
        }
    }
</style>