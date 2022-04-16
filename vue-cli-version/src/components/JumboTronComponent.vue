<template>
    <section>
        <div>
            <img :src="jumboCarosel[parseInt(imgPointerSaved)].bkgImgPath" alt="">
            <div>
                <img :src="jumboCarosel[imgPointerSaved].logoPath" alt="">
                <h3>{{ jumboCarosel[imgPointerSaved].title }}</h3>
                <p>{{ jumboCarosel[imgPointerSaved].gameDescription }}</p>
            </div>

        </div>
        <div>
            <div  @click="imgPointer(index)" :key="index" v-for="(item,index) in jumboCarosel">
                <img :src="item.thumbImgPath" alt="">
            </div>
        </div>
    </section>
</template>

<script>

import jumboBg from '@/assets/jumbo-bg.png';
import jumboLogo from '@/assets/returnal-hero-banner-logo.png';
import jumboAssetReturnal from '@/assets/returnal-listing-thumb-01-ps5.jpg'
import jumboAssetBgRetchet from '@/assets/ratchet-and-clank-rift-apart-keyart.jpg';

export default {
    name:'JumboTronComponent',
    data(){
        return{
            jumboCarosel:[
                {
                    bkgImgPath: jumboBg,
                    logoPath: jumboLogo,
                    title:'Rompi il cerchio',
                    gameDescription: 'Rialzati dopo ogni sconfitta e affronta una nuova sfida con ogni rinascita in questo esplosivo thriller fantascientifico.',
                    thumbImgPath: jumboAssetReturnal
                },
                {
                    bkgImgPath: jumboAssetBgRetchet,
                    logoPath: jumboLogo,
                    title:'Minchie Paradossali',
                    gameDescription: 'Gioca e rigioca, poi gioca ancora e rigioca ancora',
                    thumbImgPath: jumboAssetBgRetchet
                },
                {
                    bkgImgPath: jumboBg,
                    logoPath: jumboLogo,
                    title:'Rompi il cerchio',
                    gameDescription: 'Rialzati dopo ogni sconfitta e affronta una nuova sfida con ogni rinascita in questo esplosivo thriller fantascientifico.',
                    thumbImgPath: jumboAssetReturnal
                },
                {
                    bkgImgPath: jumboAssetBgRetchet,
                    logoPath: jumboLogo,
                    title:'Minchie Paradossali',
                    gameDescription: 'Gioca e rigioca, poi gioca ancora e rigioca ancora',
                    thumbImgPath: jumboAssetBgRetchet
                },
                {
                    bkgImgPath: jumboBg,
                    logoPath: jumboLogo,
                    title:'Rompi il cerchio',
                    gameDescription: 'Rialzati dopo ogni sconfitta e affronta una nuova sfida con ogni rinascita in questo esplosivo thriller fantascientifico.',
                    thumbImgPath: jumboAssetReturnal
                },
                {
                    bkgImgPath: jumboAssetBgRetchet,
                    logoPath: jumboLogo,
                    title:'Minchie Paradossali',
                    gameDescription: 'Gioca e rigioca, poi gioca ancora e rigioca ancora',
                    thumbImgPath: jumboAssetBgRetchet
                }
            ],
            imgPointerSaved: 0,
        }
    },
    methods:{
        imgPointer(p){
            this.imgPointerSaved = p
            console.log('oooh',this.imgPointerSaved);
            return p
        }
    },
    
}
</script>

<style lang="scss" scoped>
@import '../style/general';

    section{
        margin-top: 80px;
        
        & > div:first-child{
            width: 100%;
            position: relative;
            height: 650px;
            img{
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
            div{
                position: absolute;
                bottom: 100px;
                left: 100px;
                color: $white;
                img{
                    width: 40%;
                }
                h3{
                    margin: 30px 10px;
                    font-size: 2rem;
                }
                p{
                    margin: 30px 0;
                    width: 50%;
                }
            }
        }
        & > div:last-child{
            display: flex;
            justify-content: center;
            margin-top: 50px;
            div{
                margin: 0 10px;
                width: calc(100% / 6 - 3rem);
                
                img{
                    padding: 3px;
                    width: 100%;   
                    border-radius: 30px;
                    &:hover{
                        border: 4px solid $border-hover;
                        transform: translateY(-40px);
                        transition: transform 2s;
                    }
                }
            }
        }
    }
</style>