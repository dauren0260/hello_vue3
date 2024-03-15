<template>
    <div class="person">
        <h3>姓名: {{person.name}}</h3>
        <h3>年齡: {{person.age}}</h3>
        <button @click="changeName">修改姓名</button>
        <button @click="changeAge">修改年齡</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {reactive, toRefs, toRef} from 'vue'
    
    let person = reactive({
        name: 'Amy',
        age: 19
    })

    let {name, age} = person   //解構出來，此name就不是原本的person.name
    // let {name, age} = toRefs(person)   
    // let nl = toRef(person,'age')
    function changeName(){
        name += "~"
        console.log(name, person.name)
    }
    function changeAge(){
        person.age += 1
    }
    
</script>

<style scoped>
.person{
    background-color: rgb(241, 241, 241);
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
    margin-top: 50px;
}
</style>
