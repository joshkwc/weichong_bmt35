<template>
  <!-- https://tailwindcss.com/docs/guides/nuxtjs -->
  <div>
    <!-- props, passing down of data, also a form of v-bind  -->
    <TestingChild :first-name="firstName" :last-name="lastName" />
  </div>
</template>

<script>
import TestingChild from './TestingChild'
export default {
  name: 'TestingVue',
  components: { TestingChild },
  data() {
    return {
      firstName: 'Wei Chong',
      lastName: 'Kwek',
    }
  },
}
</script>
<style></style>