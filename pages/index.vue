<template>
  <div class="p-4">
    <UCard>
      <template #header>
        <h1 class="text-xl font-bold">Bem-vindo ao Nuxt UI</h1>
      </template>

      <p>Agora você está usando os componentes Nuxt UI! 🎉</p>

      <UInputMenu
        v-model="value"
        create-item
        :items="items"
        class="w-48"
        @create="onCreate"
      />
    </UCard>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const items = ref(["Backlog", "Todo", "In Progress", "Done"]);
const value = ref("Backlog");

function onCreate(item: string) {
  items.value.push(item);

  value.value = item;
}
</script>
