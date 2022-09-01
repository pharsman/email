  <template>
  <header>
    <h1>Email</h1>
  </header>
  <section>
    <InputEmail @add="addEmail" />
    <ul>
      <Email v-for="email in emails" :key="email.id" :id="email.id" :email="email.address" @deleteEmail="delEmail" />
    </ul>
  </section>
</template>

<script setup>
import Email from './components/Email.vue'
import InputEmail from './components/InputEmail.vue';

import { ref } from 'vue';
const emails = ref([
  {
    id: '123',
    address: 'test@example.com'
  },
  {
    id: '122',
    address: 'other@example.com'
  },
])

function delEmail(emailId) {
  emails.value = emails.value.filter((email) => email.id !== emailId)
}

function addEmail(address) {
  const newEmail = {
    id: String(Date.now().toString(32) + Math.random().toString(16)).replace(/\./g, ''),
    address : address
  }
  emails.value.push(newEmail)
}

</script>

<style>
* {
  margin: 0;
  padding: 0;
  text-emphasis: none;
  list-style-type: none;
  box-sizing: border-box;
}

header {
  background-color: #3E83D0;
  padding: 2rem;
  width: 40rem;
  border-radius: 10px;
  box-shadow: 0px 0px 45px -14px rgba(0, 0, 0, 0.75);
  margin: 100px auto;
}

header h1 {
  text-align: center;
  color: #fff;
  font-size: 20px;
}

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

ul {
  margin: 0 auto;
  margin-left: 33.4%;
  width: 40rem;
  display: inline-flex;
  flex-wrap: wrap;
  padding: 10px;
}
</style>

