<template>
  <!-- https://tailwindcss.com/docs/guides/nuxtjs -->
  <div>
    <h1>Component: TestingChild{{ toggleChild }}.Vue</h1>
    <button
      class="rounded-md border-black bg-blue p-5"
      @click="toggleChildButton"
    >
      Change component
    </button>
    <TestingChild1
      v-if="toggleChild === 1"
      :first-name="firstName"
      :last-name="lastName"
    />
    <TestingChild2 v-else-if="toggleChild === 2" />
    <TestingChild3 v-else />
  </div>
</template>

<script>
import TestingChild1 from './TestingChild1'
import TestingChild2 from './TestingChild2'
import TestingChild3 from './TestingChild3'
export default {
  name: 'TestingVue',
  components: { TestingChild1, TestingChild2, TestingChild3 },
  data() {
    return {
      firstName: 'Wei Chong',
      lastName: 'Kwek',
      toggleChild: 1,
    }
  },
  methods: {
    toggleChildButton() {
      if (this.toggleChild === 1) this.toggleChild = 2
      else if (this.toggleChild === 2) this.toggleChild = 3
      else this.toggleChild = 1
    },
  },
}
</script>
<style></style>
