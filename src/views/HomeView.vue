<template>
  <div v-if="toggle" class="homeView">
    <LoginFormComponent @toggleSignUp="toggle = !toggle" />
  </div>
  <div v-else class="homeView">
    <SignUpFormComponent @toggleLogin="toggle = !toggle" />
  </div>
</template>
<script>
import { ref } from 'vue'
import LoginFormComponent from '../components/LoginFormComponent.vue'
import SignUpFormComponent from '../components/SignUpFormComponent.vue'
export default {
  components: { LoginFormComponent, SignUpFormComponent },
  setup(props, context) {
    const toggle = ref(true)

    return { toggle }
  }
}
</script>
<style scoped>
.homeView {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 50px;
}
</style>
