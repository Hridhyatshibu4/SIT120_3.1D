<template>
  <div>
    <h2>Chat Portal</h2>

    <!-- Chat container -->
    <div class="chat-container">
      <!-- Chat messages -->
      <div class="chat-messages">
        <div v-for="(message, index) in chatMessages" :key="index" :class="{ 'user-message': message.fromUser }">
          {{ message.text }}
        </div>
      </div>

      <!-- User input -->
      <div class="user-input">
        <input v-model="userMessage" @keydown.enter="sendMessage" placeholder="Type your message..." />
        <button @click="sendMessage">Send</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatPortal',
  data() {
    return {
      userMessage: '',
      chatMessages: [],
    };
  },
  methods: {
    sendMessage() {
      if (this.userMessage.trim() === '') return;

      // Add the user's message to the chat
      this.chatMessages.push({ text: this.userMessage, fromUser: true });

      // Simulate a bot response (in a real implementation, you'd call a chatbot API)
      setTimeout(() => {
        this.chatMessages.push({ text: 'Bot: Hello, how can I assist you?', fromUser: false });
      }, 1000);

      // Clear the user's input
      this.userMessage = '';
    },
  },
};
</script>

<style>
/* Add your CSS styles for the chat portal here */
.chat-container {
  border: 1px solid #ccc;
  padding: 10px;
  max-width: 400px;
  margin: 0 auto;
}

.chat-messages {
  max-height: 200px;
  overflow-y: auto;
  border: 1px solid #ccc;
  padding: 10px;
  margin-bottom: 10px;
}

.user-message {
  text-align: right;
}

.user-input {
  display: flex;
  justify-content: space-between;
}

input {
  flex: 1;
  padding: 5px;
  border: 1px solid #ccc;
}

button {
  padding: 5px 10px;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}
</style>
