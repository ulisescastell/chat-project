<template>
    <div>
        <ul>
            <li v-for="(msg, index) in messages" :key="index">{{ msg }}</li>
        </ul>
        <MessageComponent :prefix="msgPrefix" @sendMsg="storeMessage"/>
    </div>
</template>

<script>
import MessageComponent from './MessageComponent.vue';

export default {
    components: {
        MessageComponent,
    },
data() {
    return {
        msgPrefix: "User 1:",
        messages: []
    }
},
methods: {
    storeMessage(message) {
        this.messages.push(message)
    }
}
};
</script>

<style scoped>
div {
  padding: 20px;
  border: 1px solid black;
  background-color: #f0f0f0;
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 5px 0;
  padding: 10px;
  background-color: #e0e0e0;
  border-radius: 4px;
}
</style>
