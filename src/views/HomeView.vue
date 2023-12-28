<script setup>
import { Presence, Motion } from "motion/vue";
import { ref } from "vue";
import TheWelcome from "../components/TheWelcome.vue";

const text = ref("<p>Hi &#x1F44B</p>");
const textShow = ref(true);
const textFinished = ref(false);

setTimeout(() => {
  textShow.value = false;
}, 3000);
setTimeout(() => {
  text.value = "You're about to land on someone's portfolio website";
  textShow.value = true;
}, 4000);
setTimeout(() => {
  textShow.value = false;
}, 6000);
setTimeout(() => {
  text.value = "Please Welcome ...";
  textShow.value = true;
}, 7000);
setTimeout(() => {
  textShow.value = false;
}, 9000);
setTimeout(() => {
  textFinished.value = true;
}, 10000);
</script>

<template>
  <div
    class="h-screen w-screen overflow-hidden bg-[#0649B5] flex justify-center items-center flex-col"
  >
    <Presence :exit-before-enter="true">
      <Motion
        v-show="textShow"
        :initial="{ opacity: 0 }"
        :animate="{ opacity: 1 }"
        :exit="{ opacity: 0 }"
        :transition="{ duration: 1 }"
        class="box text-white text-3xl"
      >
        <p v-html="text" class="text-center"></p>
      </Motion>
    </Presence>

    <TheWelcome v-if="textFinished"></TheWelcome>
  </div>
</template>

<style scoped>
.main-text {
  font-family: "Modak";
}
</style>
