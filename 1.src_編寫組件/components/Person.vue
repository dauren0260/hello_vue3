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
        data(){
            return {
                name: '艾咪',
                enName: 'Amy',
                age: 15
            }
        },
        methods:{
            showName(){
                alert(this.enName);
            },
            changeAge(){
                this.age += 1;
            }
        }
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
