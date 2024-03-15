<template>
    <div class="person">
        <h2>姓名: {{name}}</h2>
        <h2>年齡: {{age}}</h2>
        <button @click="showName">查看英文名字</button>
        <button @click="changeAge">年齡+1</button>
    </div>
    <div class="car">
        <h2>一輛{{car.brand}}車子，價值{{car.price}}萬</h2>
        <button @click="changePrice">價格+10</button>
    </div>
    <div class="game">
        <li v-for="g in games" :key="g.id">{{ g.name }}</li>
        <button @click="changeGame">修改第一個遊戲</button>
    </div>
    <div class="mountain">
        和尚的名字: {{obj.mountain.monk.name}} <br/>
        <button @click="changeObj">修改和尚名字</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {ref, reactive} from 'vue'

    let name = ref("艾咪");
    let age = ref(15);
    let enName = "Amy";
    
    let car = reactive({brand: "Toyota",price: 100})
    let games = reactive([
        {id:"sjflsdf01", name:"跑online"},
        {id:"sjflsdf02", name:"煮過頭"},
        {id:"sjflsdf03", name:"幻獸帕魯"},
    ])

    let obj = reactive({
        mountain:{
            monk:{
                name: "莫愁"
            }
        }
    })

    function showName(){
        alert(enName);
    }

    function changeAge(){
        age.value += 1
    }

    function changePrice(){
        car.price += 10
    }
    function changeGame(){
        games[0].name = "LOL"
    }
    function changeObj(){
        obj.mountain.monk.name = "莫非"
    }
</script>

<style scoped>

.person{
    background-color: rgb(241, 241, 241);
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}

.car, .game, .mountain{
    background-color: rgb(241, 241, 241);
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
    margin-top: 50px;
}
</style>
