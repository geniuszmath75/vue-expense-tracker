<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      v-for="transaction in transactions"
      :key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
    >
      <button class="btn bg-error btn-delete">
        <i class="icon icon-delete"></i>
      </button>
      {{ transaction.text }} <span>{{ transaction.amount }}zł</span>
    </li>
  </ul>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
  transactions: {
    type: Array,
    required: true,
  },
});

</script>
