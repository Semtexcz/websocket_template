<template>
  <div>
    <h1>WebSocket Chat</h1>
    <div class="messages">
      <div v-for="(msg, index) in messages" :key="index">{{ msg }}</div>
    </div>
    <input v-model="message" placeholder="Type a message" @keyup.enter="sendMessage" />
    <button @click="sendMessage">Send</button>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const messages = ref([]);
const message = ref('');
let socket;

const sendMessage = () => {
  if (message.value.trim()) {
    socket.send(message.value);
    messages.value.push(`You: ${message.value}`);
    message.value = '';
  }
};

onMounted(() => {
  socket = new WebSocket('ws://localhost:8000/ws');

  socket.onmessage = (event) => {
    messages.value.push(event.data);
  };

  socket.onclose = () => {
    messages.value.push('Connection closed');
  };
});

onUnmounted(() => {
  if (socket) {
    socket.close();
  }
});
</script>

<style>
.messages {
  border: 1px solid #ccc;
  padding: 1rem;
  height: 300px;
  overflow-y: auto;
  margin-bottom: 1rem;
}
</style>