,<template>
  <div class="container">
    <h1 class="title">Hallo,welcome to my vue app!!</h1>
    <p class="subtitle">what is your name?</p>

    <input class="input" type="text" v-model="inputText" placeholder="Type something..." />

    <div :class="{ 'red-text': isRed }" :style="{ 'font-weight': isBold ? 'bold' : 'normal' }" class="dynamic-text">
      {{ dynamicText }}
    </div>

    <div class="buttons">
      <button @click="toggleRed" class="button">{{ isRed ? 'Disable Red Text' : 'Enable Red Text' }}</button>
      <button @click="toggleBold" class="button">{{ isBold ? 'Disable Bold Text' : 'Enable Bold Text' }}</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: '', 
      isRed: false, 
      isBold: false 
    };
  },
  computed: {
    dynamicText() {
      return this.inputText.toUpperCase();
    }
  },
  methods: {
    toggleRed() {
      this.isRed = !this.isRed;
    },
    toggleBold() {
      this.isBold = !this.isBold;
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.title {
  font-size: 36px;
  margin-bottom: 20px;
}

.subtitle {
  font-size: 18px;
  margin-bottom: 20px;
}

.input {
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  border: 1px solid #e11585;
  border-radius: 5px;
  font-size: 16px;
}

.dynamic-text {
  margin-bottom: 20px;
}

.buttons {
  display: flex;
  justify-content: space-between;
}

.button {
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: #18b8b6;
  color:  #ffffff;
  transition: background-color 0.3s;
}

.button:hover {
  background-color: #3d1bea;
}

.red-text {
  color: rgb(92, 203, 234);
}
</style>