<template>
  <div>
    <input v-model="internal.firstName">
    <input v-model="internal.lastName">
    <button @click="$emit('input', internal)">Save</button>
  </div>
</template>

<script>
import { cloneDeep } from 'lodash'

export default {
  props: {
    value: Object
  },
  watch: {
    value: {
      handler(newValue) {
        this.internal = cloneDeep(newValue)
      },
      deep: true
    }
  },
  data () {
    return {
      internal: cloneDeep(this.value)
    }
  }
}
</script>