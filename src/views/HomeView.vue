<template>
  <div class="home">
    <h1>{{ header }}</h1>

    <h3>{{ counterData.title }}:</h3>

    <div>
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">++</button>
    </div>
    <p>This counter is {{ oddOrEven }}</p>
    <div class="edit">
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text" />
    </div>
  </div>
</template>

<script setup>
import {
  computed,
  onBeforeUpdate,
  onMounted,
  onUpdated,
  reactive,
  watch,
} from "vue";

const header = "This is my amazing counter";

const counterData = reactive({
  count: 0,
  title: "My counter",
});

const oddOrEven = computed(() => {
  return counterData.count % 2 == 0 ? "even" : "odd";
});

watch(
  () => counterData.count,
  (newValue) => {
    if (newValue == 2) {
      console.log("The second value is equal to 2");
    }
  }
);

const increaseCounter = (amount) => (counterData.count += amount);
const decreaseCounter = (amount) => (counterData.count -= amount);

onMounted(() => {
  console.log("OnMounted #1");
})

onMounted(() => {
  console.log("OnMounted #2");
})

</script>

<style>
.home {
  text-align: center;
  padding: 20px;
}
.btn,
.counter {
  font-size: 40px;
  margin: 10px;
}
.edit {
  margin-top: 10px;
}
</style>
