<template>
  <div class="container">
    <img src="@/assets/images/loading.png" class="loading-image" alt="loading">
    <div class="nav-buttons">
      <div class="nav-button right-top" @click="goToBasics">
        <img src="@/assets/images/dog.png" class="button-icon" alt="dog">
        <div class="button-text">
          <span>Philosophy Basics</span>
          <span class="chinese-text">哲学芝士</span>
        </div>
      </div>
      <div class="nav-button right-middle" @click="goToDaily">
        <img src="@/assets/images/dog.png" class="button-icon" alt="dog">
        <div class="button-text">
          <span>Daily Philosophy</span>
          <span class="chinese-text">每日哲学</span>
        </div>
      </div>
      <div class="nav-button left-bottom" @click="goToChat">
        <img src="@/assets/images/dog.png" class="button-icon" alt="dog">
        <div class="button-text">
          <span>Chat</span>
          <span class="chinese-text">和汪交流</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const goToBasics = () => router.push('/basics')
const goToDaily = () => router.push('/daily')
const goToChat = () => router.push('/index')
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 100vh;
  position: relative;
  background: #ffffff;
}

.loading-image {
  width: 50vw;
  height: auto;
  aspect-ratio: 1;
  position: absolute;
  top: 50%;
  left: 40%;
  transform: translate(-50%, -50%);
}

.nav-buttons {
  position: absolute;
  width: 100%;
  height: 100%;
}

.nav-button {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5px;
  filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.15));
  transition: all 0.3s ease;
  cursor: pointer;

  &:active {
    opacity: 0.8;
    transform: scale(1.1);
    filter: drop-shadow(0 6px 12px rgba(0, 0, 0, 0.2));
    background: rgba(255, 255, 255, 0.1);
    border-radius: 8px;
    padding: 5px;
  }
}

.button-icon {
  width: 52px;
  height: 52px;
  transition: transform 0.3s ease;
}

.button-text {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;

  span {
    color: #333;
    font-size: 14px;
    font-weight: 300;
    text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  .chinese-text {
    font-size: 12px;
    opacity: 0.9;
  }
}

.right-top {
  top: 500px;
  left: 30px;
}

.right-middle {
  top: 50%;
  right: 30px;
  transform: translateY(-50%);
}

.left-bottom {
  top: 60px;
  right: 75px;
}

.nav-button:active {
  .button-icon {
    transform: rotate(15deg);
  }

  .button-text span {
    transform: scale(1.05);
    color: #000;
    text-shadow: 0 3px 6px rgba(0, 0, 0, 0.15);
  }
}
</style> 