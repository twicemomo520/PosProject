<script>
import { RouterLink, RouterView } from 'vue-router'
import { useRoute, useRouter } from 'vue-router'

export default{
    data(){
        return{
        }
    },
    components:{
        RouterLink
    },
    methods:{
        goToYouTube(){
            window.open('https://www.youtube.com', '_blank');
        },
        changePage(page){
            this.currentPage = page
            useHeaderPageStore().currentHeaderPage = page
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="logo" @click="goToYouTube">
            <i class="fa-brands fa-youtube"></i>
            <h1>Premium</h1>
        </div>
        <div class="headerArea">
            <RouterLink class = "routeItem"  to="/" @click="changePage('home')" :class="{clickStyle: currentPage == 'home'}">
                <i class="fa-solid fa-house" ></i>首頁</RouterLink>

        </div>    
        <div class="login">
            <i class="fa-solid fa-user"></i>
            <h1>Login</h1>
        </div>
    </div>    
</template>

<style scoped lang = "scss">


*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Zen Kaku Gothic New", sans-serif;
}

.container{

    position: fixed;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    align-items: center;
    justify-content: flex-start;
    position: relative;
    background: #F7F7F5;
    padding: 5px;
    
    .logo{
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        i{
            font-size: 40px;
            color: red;
            margin-right: 5px; /* 调整图标和文字之间的间距 */
        }
        h1{
            font-size: 20px;
            color: black;

        }
    }
    .login{
        width: 100%;
        height: 10%;
        display: flex;
        align-items: center;
        justify-content: start;
        cursor: pointer;
        margin: 50px 0;
        padding: 0 20px;
        i{
            font-size: 20px;
            color: black;
            margin-right: 10px; /* 调整图标和文字之间的间距 */
        }
        h1{
            font-size: 20px;
            color: black;

        }
    }    

    .headerArea{

        width: 100%;
        height: 10%;
        display: flex;
        flex-direction: column;
        align-items: start;
        justify-content: space-around;
        background: #F7F7F5;
        padding-top: 30px;
        .clickStyle{
            background-color: #dee0fe;
            border-radius:  12px;       
            // border: 1px solid #7980de;
        }

        .routeItem{
            position: relative;
            width: 100%;
            height: 100%;
            font-size: 20px;
            font-weight: 500;
            color: black;
            text-decoration: none;
            cursor: pointer;

            display: flex;
            align-items: center;
            justify-content: flex-start;
            padding: 0 20px;

            i{
                margin-right: 20px; /* 调整图标和文字之间的间距 */
            }
            &:hover{
                // color: #55dde0;
                background-color: #dee0fe;
                border-radius:  12px;       
                // border: 1px solid #7980de;
            }
            &:before{
                    content: "";
                    position: absolute;
                    left: 0;
                    bottom: 0;
                    width: 100%;
                    height: 2px;
                    background-color: #3f39427c;
                }
        }
    } 

}
</style>
