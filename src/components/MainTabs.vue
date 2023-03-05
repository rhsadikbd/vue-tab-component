<template>
    <div class="tab-wrapper">
        <div class="tabs-menu">
            <button @click="tabOneHandler" :class="{'active': tabOne}">Tab One</button>
            <button @click="tabTwoHandler" :class="{'active': tabTwo}">Tab Two</button>
            <button @click="tabThreeHandler" :class="{'active': tabThree}">Tab Three</button>
        </div>
        <div class="tabs-content">
            <tab-one v-if="tabOne"/>
            <tab-two v-if="tabTwo"/>
            <tab-three v-if="tabThree"/>
        </div>
    </div>
</template>




<script>
import TabOne from './tabs/TabOne.vue'
import TabTwo from './tabs/TabTwo.vue'
import TabThree from './tabs/TabThree.vue'
    export default {
        components:{
            TabOne, TabTwo, TabThree
        },
        data(){
            return{
                tabOne: true,
                tabTwo: false,
                tabThree: false,
            }
        },
        methods: {
            tabOneHandler() {
                this.tabOne = true;
                this.tabTwo = false;
                this.tabThree = false;
            },
            tabTwoHandler() {
                this.tabOne = false;
                this.tabTwo = true;
                this.tabThree = false;
            },
            tabThreeHandler() {
                this.tabOne = false;
                this.tabTwo = false;
                this.tabThree = true;
            },
        },
    }
</script>



<style>
.tab-wrapper{
    width: 768px;
    margin: 0 auto;
}
.tabs-menu{
    text-align: center;
    border-bottom: 1px solid #e2edfa;
}
.tabs-menu button{
    color: #222;
    font-size: 14px;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
    background: transparent;
    border: none;
    padding: 10px 30px;
    border-bottom: 2px solid transparent;
    cursor: pointer;
    user-select: none;
}
.tabs-menu button.active{
    border-bottom: 2px solid #026cd1;
    color: #026cd1;
}
.tabs-content h3{
    margin-bottom: 5px;
    font-family: sans-serif;
}
.tabs-content p{
    font-family: sans-serif;
    margin: 0;
    font-size: 14px;
    color: #666;
    line-height: 20px;
}
</style>