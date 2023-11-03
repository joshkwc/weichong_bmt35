<template>
  <!-- How to use computed & props -->
  <div>{{ fullName }}</div>
</template>

<script>
export default {
  name: 'TestingChild1',
  props: {
    firstName: {
      type: String,
      default: 'Shawn',
    },
    lastName: {
      type: String,
      default: 'Choo',
    },
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`
    },
  },
}
</script>
