<template>
    <button @click="this.$emit('customAction')" :disabled="noMoreMoney">{{ toAction }}</button>
</template>

<script>
    export default {
        props: {
            toAction: String,
            noMoreMoney: {
                type: Boolean, 
                default: false, 
            }
        },
        methods: {
            customAction() {
                this.$emit('customAction')
            }
        }
    }
</script>

<style scoped>
    button {
        padding: 1rem 1.75rem;
        font-size: 1rem;
        border: none;
        color: whitesmoke;
        text-transform: uppercase;
        background-color: var(--black);
        font-weight: 700;
        margin: 0.5rem;
        border-radius: 0.5rem;
        cursor: pointer;
    }

    button:disabled {
        background-color: lightgray;
        cursor: not-allowed;
    }
</style>