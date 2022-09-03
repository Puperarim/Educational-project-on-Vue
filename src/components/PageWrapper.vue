<template>
  <div class="page__wrapper">
    <div
      v-for="pageNumber in totalPages"
      :key="pageNumber"
      class="page"
      :class="{
        'current-page': pageNumber === page,
      }"
      @click="$emit('update:page', pageNumber)"
    >
      {{ pageNumber }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    totalPages: {
      type: Number,
    },
    page: {
      type: Number,
      default: 1,
    },
  },
};
</script>

<style scoped>
.page__wrapper {
  display: flex;
  column-gap: 3px;
}
.page {
  border: 1px solid black;
  padding: 10px;
  cursor: pointer;
}
.current-page {
  border: 2px solid teal;
}
</style>