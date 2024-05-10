<template>
    <user-data
    @add-data="addData"
    ></user-data>
        <ul>
            <active-user
            v-for="(data, index) in datas"
            :key="index"
            :name="data.name"
            :age="data.age"
            ></active-user>
        </ul>
</template>

<script>
export default {
    data() {
        return{
            datas:[
                {
                    name: "Dimitra",
                    age: "30",
                }
            ]
        }
    },
  methods: {
    addData(name, age) {
        const newData = {
            name : name,
            age: age,
        }
        this.datas.push(newData);
    }
  },
    
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');

  
  html {
    font-family: 'Jost', sans-serif;
    background-color: rgb(211, 165, 246);
  }

  

</style>