<template>
  <section id="projects" class="relative w-11/12 px-16 mx-auto">
    <SectionHeader title="My Projects" />
    <!-- Custom Navigation Buttons -->
    <button
      class="swiper-prev absolute top-2/3 left-4 transform -translate-y-1/2 z-10 text-white dark:bg-secondary bg-primary p-4 rounded-full"
    >
      <Icon icon="line-md:arrow-left" class="font-bold text-3xl" />
    </button>
    <button
      class="swiper-next absolute top-2/3 right-4 transform -translate-y-1/2 z-10 text-white dark:bg-secondary bg-primary p-4 rounded-full"
    >
      <Icon icon="line-md:arrow-right" class="font-bold text-3xl" />
    </button>

    <!-- Swiper Component -->
    <swiper
      :effect="'coverflow'"
      grabCursor
      centeredSlides
      :slidesPerView="'auto'"
      :coverflowEffect="{
        rotate: 50,
        stretch: 0,
        depth: 100,
        modifier: 1,
        slideShadows: true,
      }"
      :navigation="navigationOptions"
      loop
      pagination
      :modules="[EffectCoverflow, Navigation]"
      class="max-w-full mt-32"
    >
      <swiper-slide
        class="max-w-[300px]"
        v-for="(project, index) in projects"
        :key="index"
      >
        <ProjectCard
          :title="project.title"
          :description="project.description"
          :image="'src/assets/images/' + project.image"
          :tags="project.tags"
          :liveLink="project.liveLink"
          :codeLink="project.codeLink"
        />
      </swiper-slide>
    </swiper>
  </section>
</template>

<script setup>
import SectionHeader from "@/components/Ul/SectionHeader.vue";
import ProjectCard from "@/components/Ul/ProjectCard.vue";
import "swiper/css";
import "swiper/css/effect-coverflow";
import "swiper/css/navigation";
import "swiper/css/pagination";
import { Swiper, SwiperSlide } from "swiper/vue";
import { EffectCoverflow, Navigation } from "swiper/modules";
import { ref } from "vue";

// Define navigation options
const navigationOptions = {
  prevEl: ".swiper-next",
  nextEl: ".swiper-prev",
};

const projects = ref([
  {
    title: "Portfolio Website",
    description:
      "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Totam consequatur.",
    image: "/ptoject-1.png",
    tags: ["HTML", "CSS", "Javascript"],
    liveLink: "/",
    codeLink: "/",
  },
  {
    title: "Portfolio Website",
    description:
      "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Totam consequatur.",
    image: "/ptoject-1.png",
    tags: ["HTML", "CSS", "Javascript"],
    liveLink: "/",
    codeLink: "/",
  },
  {
    title: "Portfolio Website",
    description:
      "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Totam consequatur.",
    image: "/ptoject-1.png",
    tags: ["HTML", "CSS", "Javascript"],
    liveLink: "/",
    codeLink: "/",
  },
  {
    title: "Portfolio Website",
    description:
      "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Totam consequatur.",
    image: "/ptoject-1.png",
    tags: ["HTML", "CSS", "Javascript"],
    liveLink: "/",
    codeLink: "/",
  },
  {
    title: "Portfolio Website",
    description:
      "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Totam consequatur.",
    image: "/ptoject-1.png",
    tags: ["HTML", "CSS", "Javascript"],
    liveLink: "/",
    codeLink: "/",
  },
]);
</script>

<style>
.swiper-button-prev,
.swiper-button-next {
  cursor: pointer;
}
.swiper-slide {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
