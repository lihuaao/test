<template>
    <div>
        <div>
            <p :flag = "flag1" @click = "click1" >一号</p>
            <ul v-if = "flag1 == true">
                <li>一号内容</li>
                <li>一号内容</li>
                <li>一号内容</li>
                <li>一号内容</li>
            </ul>
        </div>
        <div>
            <p :flag = "flag2" @click = "click2">二号</p>
            <ul v-if = "flag2 == true">
                <li>二号内容</li>
                <li>二号内容</li>
                <li>二号内容</li>
                <li>二号内容</li>
            </ul>
        </div>
        <div>
            <p :flag = "flag3" @click = "click3">三号</p>
            <ul v-if = "flag3 == true">
                <li>三号内容</li>
                <li>三号内容</li>
                <li>三号内容</li>
                <li>三号内容</li>
            </ul>
        </div>
        <div>
            <p :flag = "flag4" @click = "click4">四号</p>
            <ul v-if = "flag4 == true">
                <li>四号内容</li>
                <li>四号内容</li>
                <li>四号内容</li>
                <li>四号内容</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            flag1:false,
            flag2:false,
            flag3:false,
            flag4:false,
        }
    },
    methods:{
        click1(){
            if (this.flag1 == false) {
                this.flag1 = true
            } else {
                this.flag1 = false
            }
        },
        click2(){
            if (this.flag2 == false) {
                this.flag2 = true
            } else {
                this.flag2 = false
            }
        },
        click3(){
            if (this.flag3 == false) {
                this.flag3 = true
            } else {
                this.flag3 = false
            }
        },
        click4(){
            if (this.flag4 == false) {
                this.flag4 = true
            } else {
                this.flag4 = false
            }
        },
    }
}
</script>

<style lang="scss" scoped>
    *{
        margin: 0;
        padding: 0;
        list-style: none;
        text-decoration: none;
    }
    div{
        width: 500px;
        margin: 0 auto;
        div{
            width: 100%;
            p{
                cursor: pointer;
            }
        }
    }
</style>