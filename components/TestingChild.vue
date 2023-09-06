<template>
  <div>
    <!-- How component takes in props from parent -->
    <p>{{ fullName }}</p>
    <br/>

    <!-- Directives -->
    <!-- Different kind of v-bind are shown progressively-->
    
    <!-- v-bind:class, v-on (for click, @click) -->
    <button :class="{isNotShown: !show, isShown: show}" @click="showHide">Click me to show/hide (v-show)</button>
    <br/>
    <p v-show="show">Shown</p>
    <br/>

    <!-- v-bind:style, v-on (for click, @click) -->
    <button :style="sampleStyle" @click="changeBlock">Click me to change condition (v-if, v-else-if, v-else)</button>
    <br/>

    <!-- v-if v-else-if v-else -->
    <p v-if="ifElseDemo === 1">I am 1</p>
    <p v-else-if="ifElseDemo === 2">I am 2</p>
    <p v-else>I am 3</p>
    <br/>

    <!-- v-for, used  in list rendering -->
    <!-- each list must have assigned key in the form of v-bind:key, if not will throw error -->
    <p>Example of v-for</p>
    <p v-for="color in colorsArr" :key="color" :style="{backgroundColor: color}">{{ color }}</p>
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
      sampleStyle: {"background-color": 'red', 'color': 'white'},
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