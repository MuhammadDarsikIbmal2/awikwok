<template>
  <div id="app">
    <header>
      <h1>{{ title }}</h1>
    </header>
    <section>
      <p>{{ message }}</p>
      <ul>
        <li v-for="item in items" :key="item">{{ item }}</li>
      </ul>
      <form>
        <label for="inputText">Enter some text: </label>
        <input type="text" v-model="inputText" id="inputText">
      </form>
      <div :class="{'highlight': isHighlighted, 'normal': !isHighlighted}" 
           :style="{ color: textColor }">
        {{ inputText }}
      </div>
      <button @click="toggleHighlight">Toggle Highlight</button>
      <button @click="changeTextColor">Change Text Color</button>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Welcome to Vue.js Example',
      message: 'This is a dynamic webpage using Vue.js',
      items: ['Item 1', 'Item 2', 'Item 3'],
      inputText: '',
      isHighlighted: false,
      textColor: 'black'
    };
  },
  methods: {
    toggleHighlight() {
      this.isHighlighted = !this.isHighlighted;
    },
    changeTextColor() {
      this.textColor = this.textColor === 'black' ? 'blue' : 'black';
    }
  }
};
</script>

<style>
.highlight {
  background-color: yellow;
}
.normal {
  background-color: white;
}
</style>
