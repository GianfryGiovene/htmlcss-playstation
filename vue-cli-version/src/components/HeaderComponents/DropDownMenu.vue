<template>
    <div>
        <ul>
            <li><a href=""><img src="@/assets/play-menu-ico.png" alt=""></a></li>
            <li><a href=""><img src="@/assets/play-menu-ico.png" alt=""></a></li>
        </ul>
        <ul>
            <li><a href="">Link1</a></li>
            <li><a href="">Link2</a></li>
            <li><a href="">Link3</a></li>
            
        </ul>
    </div>
</template>

<script>
export default {
    name:'DropDownMenu',
}
</script>

<style lang='scss' scoped>
@import '@/style/variables';
    div{
        color: black;
        display: flex;
        flex-direction: column;
        background-color: $bg-white;
        box-shadow: 0 0 6px;
        position: absolute;
        left: 0;
        right: 0;
        ul{
            border-bottom: 1px solid black;
            padding: 10px 0;
            display: flex;
            justify-content: center;
            width: 100%;
            list-style-type: $remove;
            li{
                padding: 0 5px;
            }
        }
    }
</style>