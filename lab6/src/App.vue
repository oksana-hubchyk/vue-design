<template>
  <div>
    <MeetView
      v-if="step === 1"
      @next="goNext"
      @skip="goToRegister"
    />

    <ChatView
      v-else-if="step === 2"
      @next="goNext"
      @skip="goToRegister"
    />

    <FindView
      v-else-if="step === 3"
      @next="goNext"
      @skip="goToRegister"
    />

    <LoginView
      v-else-if="step === 4"
      @switchAuth="toggleAuth"
    />

    <RegisterView
      v-else-if="step === 5"
      @switchAuth="toggleAuth"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue'

import MeetView from './components/MeetView.vue'
import ChatView from './components/ChatView.vue'
import FindView from './components/FindView.vue'
import LoginView from './components/LoginView.vue'
import RegisterView from './components/RegisterView.vue'

const step = ref(1)   // 1=Meet, 2=Chat, 3=Find, 4=Login, 5=Register

function goNext() {
  if (step.value < 3) step.value++
}

function goToRegister() {
  step.value = 5
}

function toggleAuth() {
  step.value = step.value === 4 ? 5 : 4
}
</script>
