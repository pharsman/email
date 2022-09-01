<template>
    <form @submit.prevent="submitData" class="div">
        <label for="email">Please enter email</label>
        <input type="email" id="email" v-model.trim="inputEmail">
        <br>
        <button class="submit">Add Contact</button>
    </form>
</template>

<script setup>
import { ref } from 'vue';
const inputEmail = ref('')

const emit = defineEmits(['add'])

function submitData() {
    emit('add', inputEmail.value)
}

</script>

<style scoped>
.div {
    width: 40rem;
    border-radius: 10px;
    padding: 2rem;
    background-color: #fff;
    box-shadow: 0px 0px 45px -14px rgba(0, 0, 0, 0.75);
    margin: 0px auto;
    text-align: center;
}

label {
    margin-right: 20px;
    font-weight: bold;
}

input {
    outline: none;
}

.submit {
    margin-top: 10px;
    padding: 5px 15px;
    background-color: #FF0077;
    color: #fff;
    border: none;
    cursor: pointer;
}
</style>