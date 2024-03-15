<template>
    <div class="car">
        <h2>一輛{{car.brand}}車子，價值{{car.price}}萬</h2>
        <button @click="changeBrand">品牌變變變</button>
        <button @click="changePrice">價格+10</button>
        <button @click="changeCar">整組換掉</button>
    </div>
    <div>
        <h2>當前求和為: {{ sum }}</h2>
        <button @click="changeSum">求和+1</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {ref,reactive} from 'vue'
    
    let car = reactive({brand: "Toyota",price: 100})
    let sum = ref(0)

    function changeBrand(){
        car.brand = "BMW"
    }
    function changePrice(){
        car.price += 10
    }
    function changeCar(){
        // car = {brand: "Mazda", price: 80}  //頁面不會更新
        Object.assign(car,{brand: "Mazda", price: 80})
    }
    function changeSum(){
        sum.value += 1
    }
</script>

<style scoped>
.car{
    background-color: rgb(241, 241, 241);
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
    margin-top: 50px;
}
</style>
