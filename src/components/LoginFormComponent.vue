<template>
  <h1>Login to Your Account</h1>
  <form @submit.prevent="handleSubmit">
    <input type="text" placeholder="email" v-model="email" />
    <input type="password" placeholder="password" v-model="password" />
    <button type="submit">Login</button>
  </form>
  <h2>Have no account?</h2>
  <button @click="toggleSignUpForm" class="signup">Sign Up</button>
</template>
<script>
import { ref } from 'vue'
export default {
  setup(props, context) {
    const email = ref('')
    const password = ref('')

    const handleSubmit = () => {
      console.log(email.value, password.value)
    }

    // custom event to toggle form
    const toggleSignUpForm = () => {
      context.emit('toggleSignUp')
    }

    return { handleSubmit, toggleSignUpForm, email, password }
  }
}
</script>
<style scoped>
.signup {
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 0.6em 1.2em;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  background-color: #646cff;
  cursor: pointer;
  transition: border-color 0.25s;
}
</style>
