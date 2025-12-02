<template>
  <div>
    <MeetView v-if="step === 1" @next="goNext" :is-last-step="isLastStep" />
    <ChatView v-else-if="step === 2" @next="goNext" :is-last-step="isLastStep" />
    <FindView v-else-if="step === 3" @next="goNext" :is-last-step="isLastStep" />
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import MeetView from './components/MeetView.vue';
import ChatView from './components/ChatView.vue';
import FindView from './components/FindView.vue';

const step = ref(1); // 1 = Meet, 2 = Chat, 3 = Find


const isLastStep = computed(() => step.value === 3);

function goNext() {
  if (step.value < 3) {
    step.value++;
  }
}
</script>
