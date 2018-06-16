<template>
  <div id="app">
    <h1>{{ message }} - {{ person.firstName }} - {{ person.lastName }}</h1>
    <input v-model="message" />
    <DataEdit1 :value="person" />
    <DataEdit2 v-model="person" @input="personUpdated" />
  </div>
</template>

<script>
import DataEdit1 from './components/DataEdit1.vue'
import DataEdit2 from './components/DataEdit2.vue'

export default {
  name: 'app',
  components: {
    DataEdit1,
    DataEdit2,
  },
  data() {
    return {
      message: 'Hello, world!',
      person: { firstName: 'John', lastName: 'Doe' }
    }
  },
  methods: {
    personUpdated(newValue) {
      // eslint-disable-next-line no-console
      console.log('Person has been updated to: ', newValue)
    }
  }
}
</script>
