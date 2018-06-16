<template>
  <div>
    <input v-model="value.firstName">
    <input v-model="value.lastName">
  </div>
</template>

<script>
export default {
  props: {
    value: Object
  }
}
</script>
