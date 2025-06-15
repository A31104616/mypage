<template>
  <div>
    <div class="figure-container">
      <img 
        :src="imageUrl" 
        :alt="altText"
        @click="showNextDialog"
        class="figure-image"
      >
    </div>

    <div v-if="showDialog" class="chat-dialog" :class="{ 'fade-in': showDialog }">
      <div class="chat-bubble">
         <div v-html="currentDialog"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Figure',
  props: {
    imageUrl: {
      type: String,
      required: true
    },
    altText: {
      type: String,
      default: 'Image'
    },
     dialogs: {
      type: Array,
      default: () => [
        "歡迎來到我的網站！",
        "Check out my <a href='/intro' class='dialog-link'>portfolio</a>!",
        "Follow me on <a href='https://github.com' target='_blank' class='dialog-link'>GitHub</a>!",
        "That's all for now! Click to restart."
      ]
    }
  },
  data() {
    return {
      showDialog: false,
      currentDialogIndex: 0,
      isWaitingToClose: false
    }
  },
  computed: {
    currentDialog() {
      return this.dialogs[this.currentDialogIndex]
    }
  },
  methods: {
    showNextDialog() {
      if (this.isWaitingToClose) {
        this.isWaitingToClose = false
        this.currentDialogIndex = 0
        return
      }

      if (!this.showDialog) {
        this.showDialog = true
        return
      }

      if (this.currentDialogIndex >= this.dialogs.length - 1) {
        this.isWaitingToClose = true
        this.showDialog = false
      } else {
        this.currentDialogIndex++
      }
    },
    closeDialog() {
      this.showDialog = false
      this.isWaitingToClose = false
      this.currentDialogIndex = 0
    }
  }
}
</script>

<style scoped>
.figure-container {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 400px;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  z-index: 10;
}

.figure-image {
  width: auto;
  height: 400px;
  max-width: none;
  object-fit: contain;
  cursor: pointer;
  transition: filter 0.3s;
}

.chat-dialog {
  position: fixed;
  bottom: 420px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 20;
  animation: fadeIn 0.3s ease-in-out;
}

.chat-bubble {
  background: white;
  padding: 15px 20px;
  border-radius: 20px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  position: relative;
  max-width: 400px;
  margin-bottom: 5px;
}

.chat-bubble::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  border-width: 10px 10px 0;
  border-style: solid;
  border-color: white transparent transparent;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translate(-50%, 20px);
  }
  to {
    opacity: 1;
    transform: translate(-50%, 0);
  }
}
</style>