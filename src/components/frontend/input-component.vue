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
      if (this.inputValue <= 1) {
        return;
      }
      this.list.push(this.inputValue);
      this.inputValue = "";
      localStorage.setItem("myList", JSON.stringify(this.list));
    },
  },
  created() {
    const listJson = localStorage.getItem("myList");
    this.list = listJson ? JSON.parse(listJson) : [];
  },
};
</script>
