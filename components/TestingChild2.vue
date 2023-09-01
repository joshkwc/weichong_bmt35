<template>
  <div>
    <input v-model="name" class="rounded-md border-black bg-[lightblue]" placeholder="input name"/>
    <button
      class="rounded-md border-black bg-[#53badd]"
      @click="addToList">
      Click me to add
      </button>
      <p v-for="(l,lIndex) in list" :key="lIndex">
        id: {{l.id}} name: {{l.name}}
      </p>
  </div>
</template>

<script>
export default {
  name: 'TestingChild2',
  data() {
    return {
      list:[{
        id: 1,
        name: 'Test Name 1'
      }],
      name: 'Test Name'
    }
  },
  methods: {
    addToList() {
      const nextID = this.list.length + 1;
        this.list.push({
        id: nextID,
        name: `${this.name} ${this.name === 'Test Name' ? nextID : ''}`
      });
    }
  }
}
</script>
