<template>
    <form @submit.prevent="submitData">
        <label>Name</label>
        <input type="text" v-model="enteredName" placeholder="Write your name" @focus="isNameActive = true" @blur="isNameActive = false" :class="{ 'active': isNameActive }">
        <label>Age</label>
        <input type="text" v-model="enteredAge" placeholder="Write your age" @focus="isAgeActive = true" @blur="isAgeActive = false" :class="{ 'active': isAgeActive }">
        <button>Add data</button>
    </form>    
</template>

<script>
export default {
    emits: ['add-data'],
    data() {
        return {
            enteredName: '',
            enteredAge: '',
            isNameActive: false,
            isAgeActive: false,
        }
    },
    methods: {
        submitData() {
            this.$emit('add-data', this.enteredName, this.enteredAge );
            this.enteredName = '';
            this.enteredAge = '';
        }
    }
}
</script>

<style scoped>


form {
    display: flex;
    justify-content: center;
    font-size: 1.3rem;
    font-weight: bold;
    color: rgb(7, 31, 80);
}

input {
    margin-right: 10px;
    margin-left: 10px;
    border: solid rgb(10, 47, 120);
    color: rgb(10, 47, 120);
    font-size: 1rem;
    border-radius: 2%;
}

input.active {
  border: 1px solid  rgb(7, 31, 80);
  outline: 2px solid  rgb(7, 31, 80); 
}

button {
    color: white;
    background-color: rgb(10, 47, 120);
    border-radius: 10%;
    border: none;
    padding: 10px 10px;
    cursor: pointer;
}

button:hover {
    background-color: rgb(19, 80, 201);
}
</style>