<template>
  <div>
    {{ fullName }}
    <br />
    <!-- https://www.w3schools.com/charsets/ref_emoji_smileys.asp if interested on emoji -->
    <button @click="showHide">Click me to show/hide</button>
    <p v-show="show">&#128518;</p>
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
  },
}
</script>
