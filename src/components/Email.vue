<template>
    <li>
        <span v-if="email !== ''">{{ email }}<button class="delete" @click="deleteEmails">x</button></span>
    </li>
</template>

<script setup>
const props = defineProps({
    email: {
        type: String,
        required: true
    },
    id: {
        type: String,
        required: true
    }
})
const emit = defineEmits(['deleteEmail'])

function deleteEmails() {
    emit('deleteEmail', props.id)
}
</script>

<style scoped>
li {
    margin-left: 4px;
    margin-top: 10px;
}

span {
    background-color: #ccc;
    border-radius: 4px;
    padding: 0.3rem;
}

.delete {
    background-color: #FF0077;
    color: #fff;
    border: none;
    padding: 2px 5px;
    border-radius: 50%;
    cursor: pointer;
}
</style>