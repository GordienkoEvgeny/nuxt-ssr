<script setup>
import { ref } from 'vue';

const name = ref('');
const age = ref('');
const phone = ref('');
const isSubmit = ref(false);

const resultMessage = ref('');
async function submit() {
    isSubmit.value = true
    resultMessage.value = ''

   const { error } =  await useFetch('/api/contact', {
        method: 'post',
        body: {name: name.value, age: age.value, phone: phone.value}
    })
        name.value = ''
        age.value = ''
        phone.value = ''

    if (error.value) {
        resultMessage.value = `Error : ${error.value.data.message}`
    } else {
        console.log('success')
       resultMessage.value = `Success`
    }

    isSubmit.value = false

}

</script>
<template>
  <div class="container">
    <h1 class="contact">Contacts</h1>

    <form @submit.prevent="submit">
        <input type="text" v-model="name" placeholder="name">
        <input type="number" v-model="age" placeholder="age">
        <input type="number" v-model="phone" placeholder="phone">
        <button type="submit">{{ isSubmit ? 'loading' : 'submit' }}</button>
    </form>

    <p v-if="resultMessage">
        {{ resultMessage }}
    </p>
  </div>
</template>

<style>
.contact {
    color: green;
}
</style>