<template>
  <div>
    {{ data?.message }}
    <button @click="goTo(1)">Go to 1</button>
    <button @click="goTo(2)">Go to 2</button>
  </div>
</template>

<script setup lang="ts">
const route = useRoute();
const router = useRouter();

const routeId = computed(() => route.params.id);

const { data } = useNuxtData(`test_${routeId.value}`);

function goTo(id: number) {
  router.replace({ path: `/${id}`, query: route.query, hash: route.hash });
}
</script>
