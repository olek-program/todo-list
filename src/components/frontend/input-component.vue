<template>
  <div class="input-componemt">
    <input v-model="text" placeholder="..." />
    <button @click="addToList">Add</button>
    <div class="list">{{ score }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [],
      text: "",
    };
  },
  computed: {
    score() {
      return `Added to: %{this.lista}`;
    },
  },
  methods: {
    addToList() {
      this.list.push(this.text);
    },
  },
};
</script>
