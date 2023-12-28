<script setup>
import { animate, timeline } from "motion";
import { onMounted, ref } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
const clickedTab = ref("");

onMounted(() => {
  const homeAnimate = [".home", { y: [2000, 0] }, { duration: 0.3 }];
  const infoAnimate = [
    ".info",
    { y: [-2000, 0] },
    { duration: 0.3, at: "<", delay: 0.1 },
  ];
  const projectAnimate = [
    ".project",
    { y: [2000, 0] },
    { duration: 0.3, at: "<", delay: 0.1 },
  ];
  const contactAnimate = [
    ".contact",
    { y: [-2000, 0] },
    { duration: 0.3, at: "<", delay: 0.1 },
  ];

  timeline([homeAnimate, infoAnimate, projectAnimate, contactAnimate], {
    direction: "alternate",
    duration: 1,
  });
});

const animateIn = (name) => {
  animate(`.icon-${name}`, { y: -20 });
  animate(`.text-${name}`, { opacity: [0, 1], y: [-10, 0] });
};

const animateOut = (name) => {
  animate(`.icon-${name}`, { y: 0 });
  animate(`.text-${name}`, { opacity: 0, y: -10 });
};

const clicked = (name) => {
  setTimeout(() => {
    clickedTab.value = name;
  }, 500);
  animate(
    `.${name}`,
    { width: "100%", zIndex: "99" },
    { duration: 0.5, easing: "ease-in-out" }
  );
  switch (name) {
    case "home":
      router.push("/");
      break;
    case "info":
      router.push("/about");
      break;
    case "project":
      router.push("/projects");
      break;
    case "contact":
      router.push("/contacts");
      break;
    default:
      break;
  }
};
</script>

<template>
  <div
    class="h-screen w-screen overflow-hidden bg-[#0649B5] flex flex-col lg:flex-row justify-center items-center"
  >
    <div
      @mouseenter="animateIn('home')"
      @mouseleave="animateOut('home')"
      @click="clicked('home')"
      v-show="clickedTab == '' || clickedTab == 'home'"
      class="h-full flex-grow bg-[#0649B5] hover:lg:w-96 w-full lg:w-0 transition-all flex justify-center items-center flex-col home grayscale hover:grayscale-0"
    >
      <div
        class="p-3 md:p-10 rounded-full flex justify-center items-center border-2 lg:border-4 border-white icon-home"
      >
        <i class="pi pi-home text-xl md:text-4xl lg:text-7xl text-white"></i>
      </div>
      <p class="text-white text-2xl text-home opacity-0">HOME</p>
    </div>
    <div
      @mouseenter="animateIn('info')"
      @mouseleave="animateOut('info')"
      @click="clicked('info')"
      v-show="clickedTab == '' || clickedTab == 'info'"
      class="h-full flex-grow bg-[#F15BB5] hover:w-96 w-full lg:w-0 transition-all justify-center items-center flex-col flex info grayscale hover:grayscale-0"
    >
      <div
        class="p-3 md:p-10 rounded-full flex justify-center items-center border-2 lg:border-4 border-white icon-info"
      >
        <i class="pi pi-info text-xl md:text-4xl lg:text-7xl text-white"></i>
      </div>
      <p class="text-white text-2xl text-info opacity-0">ABOUT ME</p>
    </div>
    <div
      @mouseenter="animateIn('project')"
      @mouseleave="animateOut('project')"
      @click="clicked('project')"
      v-show="clickedTab == '' || clickedTab == 'project'"
      class="h-full flex-grow bg-[#FEB240] hover:w-96 w-full lg:w-0 transition-all justify-center items-center flex-col flex project grayscale hover:grayscale-0"
    >
      <div
        class="p-3 md:p-10 rounded-full flex justify-center items-center border-2 lg:border-4 border-white icon-project"
      >
        <i class="pi pi-list text-xl md:text-4xl lg:text-7xl text-white"></i>
      </div>
      <p class="text-white text-2xl text-project opacity-0">PROJECTS</p>
    </div>
    <div
      @mouseenter="animateIn('contact')"
      @mouseleave="animateOut('contact')"
      @click="clicked('contact')"
      v-show="clickedTab == '' || clickedTab == 'contact'"
      class="h-full flex-grow bg-[#00BBF9] hover:w-96 w-full lg:w-0 transition-all justify-center items-center flex-col flex contact grayscale hover:grayscale-0"
    >
      <div
        class="p-3 md:p-10 rounded-full flex justify-center items-center border-2 lg:border-4 border-white icon-contact"
      >
        <i class="pi pi-phone text-xl md:text-4xl lg:text-7xl text-white"></i>
      </div>
      <p class="text-white text-2xl text-contact opacity-0">CONTACTS</p>
    </div>
  </div>
</template>
