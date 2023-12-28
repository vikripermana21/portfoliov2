<!-- eslint-disable no-undef -->
<script setup>
import { animate } from "motion";
import { Motion, Presence } from "motion/vue";
import { onMounted } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();

onMounted(() => {
  animate(
    ".space",
    { opacity: [0, 1], y: [0, -10] },
    { delay: 2, duration: 0.5 }
  );
  animate(
    ".space",
    { y: [0, -10, 0] },
    { delay: 2, duration: 1, repeat: Infinity, easing: "ease-in-out" }
  );
});

onkeydown = (e) => {
  if (e.code == "Space") {
    animate(".space", { y: 0 }, { duration: 0.1 });
    animate(
      ".space",
      { opacity: [0, 1, 0], scale: 1.1 },
      { duration: 0.3, repeat: Infinity, easing: "ease-in-out" }
    );
    setTimeout(() => {
      router.push("/main-menu");
    }, 1000);
  }
};

onclick = () => {
  animate(".space", { y: 0 }, { duration: 0.1 });
  animate(
    ".space",
    { opacity: [0, 1, 0], scale: 1.1 },
    { duration: 0.3, repeat: Infinity, easing: "ease-in-out" }
  );
  setTimeout(() => {
    router.push("/main-menu");
  }, 1000);
};

ontouchstart = () => {
  animate(".space", { y: 0 }, { duration: 0.1 });
  animate(
    ".space",
    { opacity: [0, 1, 0], scale: 1.1 },
    { duration: 0.3, repeat: Infinity, easing: "ease-in-out" }
  );
  setTimeout(() => {
    router.push("/main-menu");
  }, 1000);
};
</script>

<template>
  <Presence>
    <Motion
      :initial="{ opacity: 0, y: 100 }"
      :animate="{ opacity: 1, y: 0 }"
      :exit="{ opacity: 0 }"
      :transition="{ duration: 1 }"
    >
      <p
        class="text-7xl lg:text-[10rem] main-text leading-none my-5 text-center bg-clip-text text-transparent bg-gradient-to-br from-[#9B5DE5] to-[#FEB240]"
      >
        VIKRI <br />
        PERMANA
      </p>
    </Motion>
  </Presence>
  <p class="text-white space text-md lg:text-xl">
    Press Space / Tap to Explore
  </p>
</template>

<style scoped>
.main-text {
  font-family: "Modak";
}
.space {
  font-family: "Urbanist";
}
</style>
