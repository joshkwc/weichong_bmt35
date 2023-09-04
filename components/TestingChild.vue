<template>
  <div>
    <p>{{ fullName }}</p>
    <button :class="{isNotShown: !show, isShown: show}" @click="showHide">Click me to show/hide</button>
    <p v-show="show">Shown</p>
    <p>
      <button :style="sampleStyle3" @click="changeBlock">Click me to change block</button>
    </p>
    <p v-if="ifElseDemo === 1">I am 1</p>
    <p v-else-if="ifElseDemo === 2">I am 2</p>
    <p v-else>I am 3</p>
    <p v-for="color in colorsArr" :key="color" :style="{backgroundColor: color}">XXX</p>
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
      colorsArr: ['red', 'blue', 'lightgreen', 'grey'],
      sampleStyle1: {"background-color": 'red'},
      sampleStyle2: {"background-color": 'cyan'},
      sampleStyle3: {"background-color": 'silver'},
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
      if (this.ifElseDemo === 1) 
        this.ifElseDemo = 2;
      else if (this.ifElseDemo === 2) 
        this.ifElseDemo = 3;
      else 
        this.ifElseDemo = 1;
    },
  },
}
</script>
<style>
.isShown{
  background-color: blue;
  color: white;
}
.isNotShown{
  background-color: brown;
  color: white;
}
</style>