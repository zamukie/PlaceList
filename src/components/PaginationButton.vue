<template>
<button class="myButton" :class="buttonClass" :type="htmlType ? htmlType : 'button'" @click="callback" :disabled="loading || disabled">
    <div class="text">{{ text }}</div>
</button>
</template>

<script>
export default {
    props: ['text', 'loading', 'type', 'icon', 'htmlType', 'disabled'],
    computed: {
        buttonClass() {
            return {
                'disabled': this.loading || this.disabled,
                [this.type]: this.type,
            }
        }
    },
    methods: {
        callback(event) {
            this.$emit('click', event)
        }
    }
}
</script>

<style scoped>
.myButton {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 12px 0;
    border-radius: 8px;
    font-size: 1rem;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
    background-color: #FFF;
    color: #333;
    border: 1px solid #134b8a;
}

.myButton:hover {
    box-shadow: 0px 0px 10px #C4D3E9;
    background-color: #C4D3E9;
    border: 1px solid #134b8a;
}

.myButton .icon {
    width: 16px;
    height: 16px;
    margin-right: 5px;
}

.myButton.primary {
    background-color: #134b8a;
    border: none;
    color: #FFF;
}

.myButton.primary:hover {
    background-color: #134b8a;
}

.myButton .spin {
    border: 2px solid #FFFAFA;
    border-radius: 50%;
    border-top: 2px solid #333;
    width: 1rem;
    height: 1rem;
    -webkit-animation: spin 2s linear infinite;
    /* Safari */
    animation: spin 2s linear infinite;
    margin-right: 5px;
}

.myButton.disabled {
    cursor: not-allowed;
}
</style>
