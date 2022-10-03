<template>
  <div class="list-group-item mb-2 card shadow-sm bg-body rounded">
    <p class="fw-semibold">{{ values.title }}</p>
    <div class="d-flex justify-content-around">
      <p>Created: {{ values.createDate }}</p>
      <p class="text-danger">Deadline: {{ values.deadlineDate }}</p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    values: Object,
    color: { type: String, required: true },
  },
};
</script>
<style scoped lang="scss">
.card {
  cursor: move;
}
</style>
