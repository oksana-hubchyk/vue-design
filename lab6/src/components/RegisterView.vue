<!-- src/components/RegisterView.vue -->
<template>
  <div class="register-screen">
    <div class="container">
      <header>
        <div class="logo">
          <svg viewBox="0 0 24 24">
            <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5
                     2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09
                     C13.09 3.81 14.76 3 16.5 3
                     19.58 3 22 5.42 22 8.5
                     c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/>
          </svg>
        </div>
        <h1>FATED</h1>
      </header>

      <div class="tabs">
        <button class="tab" @click="emitSwitch">LOGIN</button>
        <button class="tab active">REGISTER</button>
      </div>

      <input type="text" placeholder="user name">
      <input type="password" placeholder="password">
      <input type="email" placeholder="email">

      <a href="#" class="forgot">FORGOT PASSWORD?</a>

      <button class="register-btn">REGISTER</button>

      <div class="bottom-text">
        ALREADY HAVE AN ACCOUNT?
        <a href="#" @click.prevent="emitSwitch">LOGIN</a>
      </div>
    </div>
  </div>
</template>

<script setup>
const emit = defineEmits(["switchAuth"])

function emitSwitch() {
  emit("switchAuth")
}
</script>

<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
}

.register-screen {
  background-color: #ff5a5f;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  color: white;
  text-align: center;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: min(85vw, 300px);
  transition: all 0.2s ease;
}

header {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin-bottom: 3vh;
  transform: translateY(5%);
}

.logo {
  position: relative;
  width: clamp(60px, 25vw, 90px);
  aspect-ratio: 1/1;
  border-radius: 50%;
  background-color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

.logo svg {
  width: 60%;
  height: 60%;
  fill: #ff5a5f;
  transform: rotate(20deg);
}

h1 {
  font-family: "Chewy", system-ui;
  font-weight: 400;
  margin-top: 10px;
  font-size: clamp(28px, 8vw, 46px);
}

.tabs {
  display: flex;
  justify-content: center;
  width: 80%;
  margin-bottom: 15px;
  margin-top: 45px;
  gap: 15px;
}

.tab {
  flex: 1;
  background-color: rgba(255,255,255,0.3);
  border: none;
  padding: 4px 0;
  border-radius: 3px;
  color: white;
  font-weight: bold;
  cursor: pointer;
  font-size: clamp(8px, 3vw, 12px);
}

.tab.active {
  background-color: white;
  color: #ff5a5f;
}

input {
  width: 80%;
  padding: clamp(8px, 2.5vw, 12px);
  margin: 4px 0;
  border: none;
  border-radius: 4px;
  font-size: clamp(8px, 3vw, 12px);
  text-align: center;
}

.forgot {
  width: 80%;
  text-align: right;
  display: block;
  font-size: clamp(6px, 2vw, 8px);
  color: white;
  opacity: 0.9;
  margin-top: 12px;
}

.register-btn {
  width: 80%;
  margin-top: 18px;
  background-color: white;
  color: #ff5a5f;
  border: none;
  padding: clamp(8px, 2.5vw, 12px);
  border-radius: 4px;
  font-weight: bold;
  cursor: pointer;
  font-size: clamp(8px, 3vw, 12px);
}

.bottom-text {
  margin-top: 25px;
  font-size: clamp(6px, 2vw, 8px);
  opacity: 0.9;
}

.bottom-text a {
  color: white;
  font-weight: bold;
  text-decoration: none;
  margin-left: 4px;
}
</style>
