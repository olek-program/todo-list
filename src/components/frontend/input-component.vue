<template>
  <div>
    <input type="text" v-model="inputValue" />
    <button @click="addToList">Add to List</button>
    <ul>
      <li v-for="item in list" :key="item">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: "",
      list: [],
    };
  },
  methods: {
    addToList() {
      this.list.push(this.inputValue);
      this.inputValue = "";
    },
  },
};
</script>
