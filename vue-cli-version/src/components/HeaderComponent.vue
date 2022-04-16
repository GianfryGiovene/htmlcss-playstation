<template>
    <header>
        <div>
            <img src="@/assets/sony_logo.svg" alt="">
        </div>
        <div>
            <div>
                <img src="@/assets/play_logo.svg" alt="">
                <ul>
                    <li  @mouseover="item.clicked = true" @mouseleave="item.clicked = false" :key="index" v-for="(item,index) in navBar">
                        <div>{{ item.name }}</div>
                        <DropDownMenu v-if="item.clicked" />
                    </li>
                    <li><a href="#">Accedi</a></li>
                </ul>
            </div>
            
        </div>
    </header>
</template>

<script>
import DropDownMenu from './HeaderComponents/DropDownMenu.vue'
export default {
    name:'HeaderComponent',
    components:{
        DropDownMenu,
    },
    props:{
        navBar: Array,
    },   
}
</script>

<style lang="scss" scoped>
@import '../style/general';
    header{
        width: 100%;
        border: 1px dashed red;
        height: 80px;
        z-index: 10000;
        position: fixed;
        & > div:first-child{
                background-color: $bg-black;
                display: flex;
                justify-content: end;
                align-items: center;
                img{
                    padding: 8px 0 ;
                    width: 100px;
                }
        }
        & > div:last-child{
            background-color: $bg-white;
            width: 100%;
            
                div{
                    display: flex;
                    align-items: center;
                    
                    img{
                        width: 50px;
                    }
                    ul{ 
                        display: flex;
                        align-items: center;
                        list-style-type: $remove;
                        li{
                            padding: 0 10px;
                            cursor: pointer;
                            &:hover{
                                color: blue;
                            }
                            div{
                                padding: 5px 10px ;
                            }
                            a{
                                display: block;
                                display: inline-block;
                                text-decoration: none;
                                padding: 5px 10px;
                                color: $button-font-color;
                                background-color: $bg-button-primary;
                                border-radius: 20px;
                            }
                        }
                    } 
                }   
        }
    }
</style>