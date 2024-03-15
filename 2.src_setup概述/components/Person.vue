<template>
    <div class="person">
        <h2>姓名: {{name}}</h2>
        <h2>年齡: {{age}}</h2>
        <button @click="showName">查看英文名字</button>
        <button @click="changeAge">年齡+1</button>
    </div>
</template>

<script lang="ts">
    export default {
        name: 'Person',
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
            // 將數據、方法交出去，模板中才可以使用
            return {name, age, enName,showName,changeAge}

            // setup的返回值也可以是一個渲染函數
            // return ()=> '哈哈'
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
