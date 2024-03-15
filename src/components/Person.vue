<template>
    <div class="person">
        姓: <input type="text" v-model="firstName"> <br>
        名: <input type="text" v-model="lastName"> <br>
        全名: <span>{{ fullName }}</span> <br>
        <button @click="changeFullName">將全名改為Amy-Sandy</button>
    </div>
</template>

<script setup lang="ts" name="Person">
    import {ref, computed} from 'vue'
    
    let firstName = ref("John")
    let lastName = ref("Willson")

    // 這樣定義的是只讀的computed屬性
    // let fullName = computed(()=>{
    //     return firstName.value + "-" + lastName.value
    // })

    let fullName = computed({
        get(){
            return firstName.value + "-" + lastName.value
        },
        set(val){
            const [str1,str2] = val.split("-")
            firstName.value = str1
            lastName.value = str2
        }
    })

    function changeFullName() {
        fullName.value = "Amy-Sandy"
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
