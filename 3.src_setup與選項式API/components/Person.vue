<template>
    <div class="person">
        <h2>姓名: {{name}}</h2>
        <h2>年齡: {{age}}</h2>
        <button @click="showName">查看英文名字</button>
        <button @click="changeAge">年齡+1</button>
        <h3>{{ a }} , {{ b }}</h3>
        <h3><button @click="c">函數C</button></h3>
    </div>
</template>

<script lang="ts">
    export default {
        name: 'Person',
        data() {
            return {
                a: 100,
                b: this.name
            }
        },
        methods:{
            c(){
                console.log("c")
            }
        },
        setup() {
            let name = "艾咪";
            let age = 15;
            let enName = "Amy";

            function showName(){
                alert(enName);
            }

            function changeAge(){
                age += 1
            }

            return {name, age, enName,showName,changeAge}
        },
    }
    
</script>

<style scoped>

.person{
    background-color: rgb(241, 241, 241);
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}
</style>
