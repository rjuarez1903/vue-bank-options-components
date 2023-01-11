<template>
    <h2>Balance: {{ balance }}</h2>
    <h2>Account: {{ state ? 'Active' : 'Not active' }}</h2>
    <h3>Services</h3>
    <ul>
        <li v-for="(service, index) in services" :key="index">
            {{ index + 1 }} - {{ service.toLocaleUpperCase() }}
        </li>
    </ul>
    <BalanceAction 
        toAction="Augment balance"
        @customAction="augment"
    />
    <BalanceAction 
        toAction="Decrement balance"
        @customAction="decrement"
        :noMoreMoney="noMoreMoney"
    />
</template>

<script>
import BalanceAction from './BalanceAction.vue'

    export default {
        name: 'Account',
        components: {
            BalanceAction
        },
        data() {
            return {
                balance: 1000,
                account: 'Visa',
                state: false, 
                services: ['deposits', 'transferences'],
                noMoreMoney: false
            }
        },
        methods: {
            augment() {
                this.balance = this.balance + 100
                this.noMoreMoney = false
            },
            decrement() {
            if (this.balance === 0) {
                alert(`You're out of money`)
                this.noMoreMoney = true
            } else {
                this.balance = this.balance - 100
            }
            }

        }
    }
</script>

<style scoped>
    h2 {
        color: var(--black);
    }

    ul {
        list-style: none;
        padding-left: 0;
    }
</style>