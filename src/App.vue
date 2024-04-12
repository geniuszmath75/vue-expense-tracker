<template>
  <Header />
  <div class="container">
    <Balance />
    <IncomeExpenses/>
    <TransationList :transactions="transactions"/>
    <AddTransaction />
  </div>
</template>

<script setup>
import Header from "./components/Header.vue";
import Balance from "./components/Balance.vue";
import IncomeExpenses from "./components/IncomeExpenses.vue";
import TransationList from "./components/TransactionList.vue";
import AddTransaction from "./components/AddTransaction.vue";

import { ref, computed } from 'vue';

const transactions = ref([
  { id: 1, text: "Chleb", amount: -8.99 },
  { id: 1, text: "Laptop", amount: -4999.99 },
  { id: 1, text: "Pensja", amount: 3.998 },
  { id: 1, text: "Stary telefon", amount: 700 },
]);

const total = computed(() => {
  return transactions
});
</script>

<style scoped></style>
