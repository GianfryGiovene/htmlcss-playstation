<template>
    <section>
        <div>
            <span>PLAY HAS NO LIMITS</span>
            <h2>Ecco la PlayStation 5</h2>
            <span>Tuffati in nuove possibilità di gioco completamente inaspettate</span>
        </div>
        <div>
            <div>
                <h3>{{ jumboCarosel[imgPointerSaved].title }}</h3>
                <p>{{ jumboCarosel[imgPointerSaved].gameDescription }}</p>
            </div>
            <img :src="jumboCarosel[parseInt(imgPointerSaved)].bkgImgPath" alt="">
        </div>
        
        <div>
            <div  @click="imgPointer(index)" :key="index" v-for="(item,index) in jumboCarosel">
                <img :src="item.bkgImgPath" alt="">
                <h3>{{ item.title }}</h3>
            </div>
        </div>
    </section>
</template>

<script>

import consoleSony from '@/assets/playstation-5-thumb.png'
import controllerSony from '@/assets/joypad-thumb.png';
import cuffieSony from '@/assets/headset-thumb.png'
import telecomandoSony from '@/assets/remote-thumb.png';
import telecameraSony from '@/assets/camera-thumb.jpg'

export default {
    name:'SectionCaroselComponent',
    data(){
        return{
            jumboCarosel:[
                {
                    bkgImgPath: consoleSony,
                    title:'Console PS5',
                    gameDescription: 'Sperimenta cose con nuove generazioni PLAY.',
                },
                {
                    bkgImgPath: controllerSony,
                    title:'Controller per controllare',
                    gameDescription: 'Esperimenta con nuove generazioni PLAYcose.',
                },
                {
                    bkgImgPath: cuffieSony,
                    title:'Cuffie Wirless per ascoltare',
                    gameDescription: 'Sussurri nello spazio.',
                },
                {
                    bkgImgPath: telecomandoSony,
                    title:'Telecomando Medio',
                    gameDescription: 'Sai dove to ficchi sto tele?.',
                },
                {
                    bkgImgPath: telecameraSony,
                    title:'Telecamera',
                    gameDescription: 'Ignude Quamquem vicere.',
                },
                
            ],
            imgPointerSaved: 0,
        }
    },
    methods:{
        // salvo la posizione su cui ho cliccato per riutilizzarla altrove
        imgPointer(p){
            this.imgPointerSaved = p
            return p
        }
    },
}
</script>

<style lang="scss" scoped>
@import '@/style/general';

    section{
            margin: 80px auto 0; 
            max-width: 1200px;
            border: 1px solid green;
            
        & > div:first-child{
            text-align: center;
            margin-bottom: 60px;

            span:first-child{
                color: $span-secondary;
            }
            h2{
                font-size: $h2-font-size;
            }
            span:last-child{
                font-size: $span-font-size;
            }
        }
        & > div:nth-child(2){
            width: 100%;
            display: flex;
            justify-content: end;
            img{
                width: 50%;
            }
            div{
                color: $bg-black;
                img{
                    width: 100%;
                }
                h3{
                    margin: 30px 10px;
                    font-size: $h2-font-size;
                }
                p{
                    margin: 30px 0;
                    font-size: $span-font-size;
                    width: 50%;
                }
            }
        }
        & > div:last-child{
            display: flex;
            justify-content: center;
            margin-top: 50px;
            div{
                margin: 20px 10px;
                width: calc(100% / 5 - 1rem);
                &:hover{
                        border-bottom: 4px solid $border-hover;
                    }
                img{
                    padding: 3px;
                    width: 90%;   
                }
                h3{
                    padding: 0 10px;
                }
            }
        }
    }
</style>