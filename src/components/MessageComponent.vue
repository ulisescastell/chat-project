<template>
    <div>
        <form @submit="sendMsg">
            <input v-model="inputValue" type="text" name="text" placeholder="Type here...">
            <button ref="buttonRef" type="submit">
                <span>Send</span>
                <div class="success">
                    <svg xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" viewBox="0 0 29.756 29.756"
                        style="enable-background:new 0 0 29.756 29.756;" xml:space="preserve">
                        <path
                            d="M29.049,5.009L28.19,4.151c-0.943-0.945-2.488-0.945-3.434,0L10.172,18.737l-5.175-5.173 c-0.943-0.944-2.489-0.944-3.432,0.001l-0.858,0.857c-0.943,0.944-0.943,2.489,0,3.433l7.744,7.752 c0.944,0.943,2.489,0.943,3.433,0L29.049,8.442C29.991,7.498,29.991,5.953,29.049,5.009z" />
                    </svg>
                </div>
            </button>
        </form>
    </div>
</template>

<script>


export default {
    props: {
        prefix: {
            type: String,
            required: true
        },
    },
    methods: {
        sendMsg(event){
            event.preventDefault();
            if (this.inputValue.trim()) {
                this.$emit('sendMsg', this.prefix + " " + this.inputValue )
                this.inputValue = ''
                this.active(this.$refs.buttonRef)
            }
        },
        active(button){
        if (button) {
        button.classList.add("is_active")
        setTimeout(() => {
            button.classList.remove("is_active")
        }, 500)
    }
}
    },
    data() {
        return {
            inputValue: ''
        }
    },
};
</script>

<style scoped>

form {
  margin-bottom: 20px;
}

input {
  padding: 10px;
  margin-right: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    ;
    position: relative;
    width: 170px;
    height: 40px;
    line-height: 1;
    font-size: 18px;
    font-weight: bold;
    border: 1px solid #ccc;
    background: EBECF0;
    color: #505050;
    border-radius: 40px;
    cursor: pointer;
    overflow: hidden;
    transition: all .35s;
}

button:hover {
    background: #d6d4e1;
}

button span {
    opacity: 1;
    visibility: visible;
    transition: all .35s;
}

.success {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #fff;
    border-radius: 50%;
    z-index: 1;
    opacity: 0;
    visibility: hidden;
    transition: all .35s;
}

.success svg {
    width: 20px;
    height: 20px;
    fill: yellowgreen;
    transform-origin: 50% 50%;
    transform: translateY(-50%) rotate(0deg) scale(0);
    transition: all .35s;
}

button.is_active {
    width: 40px;
    height: 40px;
}

button.is_active .success {
    opacity: 1;
    visibility: visible;
}

button.is_active .success svg {
    margin-top: 50%;
    transform: translateY(-50%) rotate(720deg) scale(1);
}

button.is_active span {
    opacity: 0;
    visibility: hidden;
}
</style>
