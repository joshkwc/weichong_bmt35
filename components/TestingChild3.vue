<template>
  <div>
    <button
      class="rounded-md border-black bg-[#53badd]"
      @click="toggleShowHide">
      Click me to show/hide
      </button>
      <!-- https://www.w3schools.com/charsets/ref_emoji_smileys.asp if interested on emoji -->
      <p v-show="show">&#128518;</p>
  </div>
</template>

<script>
export default {
  name: 'TestingChild3',
  data() {
    return {
      show: true
    }
  },
  methods: {
    toggleShowHide() {
      this.show = !this.show;
    }
  }
}
</script>
