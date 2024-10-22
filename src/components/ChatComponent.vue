<template>
    <div>
        <MessageComponent :message="msg"/>
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
        msg: "Hello from father component"
    }
}
};
</script>

<style scoped>

</style>