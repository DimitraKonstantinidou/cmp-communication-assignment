<template>
    <div>
        <h2> Name: {{ name}},</h2>
        <h2>Age: {{ age }}</h2>
    </div>
</template>

<script>
export default {
    props:["name","age"]
}
</script>

<style scoped>

h2 {
    font-size: 1.3rem;
    margin-right: 15px;
    color:rgb(255, 255, 255);
}

div {
    display: flex;
    flex-direction: row;
}

</style>