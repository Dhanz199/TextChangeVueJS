<script setup>
import ButtonChange from "./components/ButtonChange.vue";
import HelloAll from "./HelloAll.vue";
import Footer from "./components/Footer.vue";
import { useCounterStore } from "./stores/counter";

const counter = useCounterStore();
const increment = () => {
  counter.$patch((state) => {
    state.count++;
  });
};

const reset = () => {
  counter.$reset();
};
</script>

<template>
  <main>
    <HelloAll :message="text" />

    <ButtonChange @change="changeText" />

    <hr />
    <Footer />

      <button class="btn btn-primary mt-2 me-3" @click="increment">
    Increment
  </button>

  <button class="btn btn-primary mt-2" @click="reset">Reset</button>
  </main>
</template>

<script>
export default {
  name: "App",
  components: {
    HelloAll,
    ButtonChange
  },
  data() {
    return {
      text: "Hello All"
    };
  },
  methods: {
    changeText() {
      this.text = "Morning All";
    },
    resetText() {
      this.text = "asdasda All";
    }
  }
};
</script>
