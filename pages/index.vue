<script setup lang="ts">
import { ref } from "vue";

const items = ref(["Backlog", "Todo", "In Progress", "Done"]);
const value = ref("Backlog");

function onCreate(item: string) {
  items.value.push(item);

  value.value = item;
}
</script>

<template>
  <div class="p-4">
    <UCard>
      <template #header>
        <h1 class="text-xl font-bold">Bem-vindo ao Nuxt UI</h1>
      </template>

      <p>Testa da autalização du NuxtUi 3.0.2</p>

      <UModal title="Modal with title">
        <UButton
          icon="i-lucide-plus"
          size="md"
          color="primary"
          variant="solid"
        />

        <template #body>
          <Placeholder class="h-48" />
          <UInputMenu
            v-model="value"
            create-item
            :items="items"
            class="w-48"
            @create="onCreate"
          />
        </template>
      </UModal>
    </UCard>
  </div>
</template>
