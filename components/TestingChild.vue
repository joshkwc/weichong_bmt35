<template>
  <div>
    <p>{{ fullName }}</p>
    <button @click="showHide">Click me to show/hide</button>
    <p v-show="show">Shown</p>
    <p>
      <button @click="changeBlock">Click me to change block</button>
    </p>
    <p v-if="ifElseDemo === 1">I am 1</p>
    <p v-else-if="ifElseDemo === 2">I am 2</p>
    <p v-else>I am 3</p>
  </div>
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
  data() {
    return {
      show: true,
      ifElseDemo: 1,
    }
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`
    },
  },
  methods: {
    showHide() {
      this.show = !this.show
    },
    changeBlock() {
      if (this.ifElseDemo === 1) this.ifElseDemo = 2
      else if (this.ifElseDemo === 2) this.ifElseDemo = 3
      else this.ifElseDemo = 1
    },
  },
}
</script>
