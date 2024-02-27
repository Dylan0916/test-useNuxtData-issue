<template>
  default layout
  <slot></slot>
</template>

<script setup>
const route = useRoute();

const routeId = computed(() => route.params.id);

await useAsyncData(
  `test_${routeId.value}`,
  () => $fetch('https://run.mocky.io/v3/b03c800b-77f2-429d-9fe6-55d1bd630ab1'),
  { watch: [routeId] }
);
</script>

<style lang="scss" scoped></style>
