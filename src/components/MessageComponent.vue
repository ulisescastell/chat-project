<template>
    <div>
        <form @click="sendMsg">
        <input type="text" name="text" placeholder="Type here...">
        <button type="submit">Send</button>
        </form>
    </div>
</template>

<script>
export default {
    props: {
        message: {
            type: String,
            required: true
        },
    },
    methods: {
        sendMsg(msg){
            msg.preventDefault();
            this.$emit('sendMsg', this.message)
        }  
    },
};
</script>

<style scoped>

</style>