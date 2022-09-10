<template>
  <div class="absolute top-2 right-2 z-10">
    <v-button href="https://github.com/xolider/vicart.ovh"><i class="fa-brands fa-github"></i> Code source</v-button>
  </div>
  <div class="h-screen w-screen bg-gradient-to-tr from-sky-600 to-green-400 fixed">
    <div class="text-white relative top-24 md:top-1/3 flex flex-col h-5/6 md:h-2/3 justify-around">
      <div class="flex flex-col-reverse md:flex-row items-center justify-center md:justify-around">
        <div class="text-center">
          <h1 class="relative font-bold text-5xl md:text-7xl drop-shadow-lg text-center mt-20 md:mt-0" :style="{right: y + 'px'}">Clément Vicart</h1>
          <small class="text-md relative top-1 px-2 md:px-0" :style="{right: y + 'px'}">Développeur Fullstack, Vue.JS, Spring Boot/Java/Kotlin, Android et C#/.NET</small>
        </div>
        <v-vertical-divider class="h-56 hidden md:block"></v-vertical-divider>
        <img src="./assets/photo.webp" alt="photo" class="relative rounded-full ring-white ring-4 w-1/3 md:w-1/6 shadow-lg" :style="{left: y + 'px'}" ref="photo">
      </div>
      <div>
        <div class="text-center text-2xl">
          <a href="https://github.com/xolider" class="hover:text-yellow-400 transition-all duration-75"><i class="fa-brands fa-github mr-6"></i></a>
          <a href="mailto:clement@vicart.dev" class="hover:text-yellow-400 transition-all duration-75"><i class="fa-solid fa-envelope"></i></a>
        </div>
        <div class="w-full flex justify-center mt-20">
          <v-button href="https://www.malt.fr/profile/clementvicart">Contactez-moi</v-button>
        </div>
      </div>
      <div class="w-full text-center mt-5 animate-bounce">
        <i class="fa-solid fa-arrow-up"></i>
      </div>
    </div>
  </div>
  <div class="relative top-98-screen bg-slate-100 rounded-t-xl w-full md:w-5/6 mx-auto">
    <div class="p-3 md:p-8">
      <h2>A propos de moi</h2>
      <div class="shadow-md py-4 bg-white mt-6 flex flex-col md:flex-row justify-around items-center">
        <img src="./assets/photo.webp" alt="photo" class="rounded-full w-1/3 md:w-2/12 shadow-lg" ref="photoText">
        <p class="text-justify break-words md:w-1/2 p-6 md:p-0" ref="textDesc">Je m'appelle Clément Vicart et suis actuellement en 5e année d'école d'Ingénieurs spécialité informatique à CESI.
        Je vous accompagnerai dans la réalisation de vos projets de développement, notamment en Web fullstack en <span class="text-violet-400 font-extrabold">HTML/CSS/Vue.JS</span> et
        <span class="text-orange-400 font-extrabold">Spring Boot/Express</span>, mais aussi en <span class="text-fuchsia-500 font-extrabold">Java/Kotlin</span>,
          <span class="text-green-500 font-extrabold">Android</span> et <span class="text-blue-400 font-extrabold">C#/.NET</span></p>
        <div class="flex flex-col mt-10 md:mt-0">
          <p>Développement Java/Kotlin/Spring Boot <i class="fa-brands fa-java text-orange-500"></i></p>
          <v-progress-bar :value="85" pgb-class="bg-orange-500"></v-progress-bar>
          <p class="mt-3">Développemen Web <i class="fa-brands fa-vuejs text-violet-600"></i></p>
          <v-progress-bar :value="75" pgb-class="bg-violet-600"></v-progress-bar>
          <p class="mt-3">Développement Android <i class="fa-brands fa-android text-green-600"></i></p>
          <v-progress-bar :value="80" pgb-class="bg-green-600"></v-progress-bar>
          <p class="mt-3 align-middle">Développement C#/.NET <img width="12" class="inline align-middle" alt="csharp-icon" src="./assets/csharp.svg"></p>
          <v-progress-bar :value="60" pgb-class="bg-indigo-700"></v-progress-bar>
        </div>
      </div>
      <h2 class="mt-10 mb-5">Compétences</h2>
      <div class="flex flex-wrap">
        <div v-for="skill in skills" :key="skill.title" class="shadow-md p-4 flex-grow md:basis-1/4 md:mx-4 mb-4 bg-white">
          <i :class="skill.icon + ' ' + skill.color" class="text-5xl"></i>
          <h3 class="my-4">{{skill.title}}</h3>
          <p class="font-light">{{skill.text}}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.top-98-screen {
  top: 98vh;
}

h2 {
  @apply text-4xl text-transparent font-bold bg-clip-text bg-gradient-to-tr from-sky-600 to-green-400;
}

h3 {
  @apply text-3xl font-medium;
}
</style>

<script lang="ts">
import VVerticalDivider from "./components/VVerticalDivider.vue";
import VButton from "./components/VButton.vue";
import {defineComponent, ref, watch} from "vue";
import VProgressBar from "./components/VProgressBar.vue";
import {useElementVisibility, useWindowScroll} from "@vueuse/core";
import {MotionVariants, useMotion} from "@vueuse/motion";


export default defineComponent({
  components: {VProgressBar, VButton, VVerticalDivider},
  setup() {
    const { y } = useWindowScroll()

    const skills = [
      {
        icon: 'fa-brands fa-java',
        title: 'Java/Kotlin',
        text: 'Le Java/Kotlin est le langage que j\'ai le plus travaillé dans mon parcours personnel et dans mon cursus professionnel.' +
            ' Allié à Spring Boot, je peux construire des systèmes back-end puissants. Je connais également l\'API JavaFX pour des apps graphiques',
        color: 'text-orange-500'
      },
      {
        icon: 'fa-brands fa-vuejs',
        title: 'Web/Vue.JS',
        text: 'TypeScript est le langage que j\'utilise le plus pour le Web, allié avec HTML5 et CSS3. Avec le framework Vue.JS (v2 & v3), ' +
            'offrez-vous des sites web dynamiques et rapides',
        color: 'text-green-500'
      },
      {
        icon: 'fa-solid fa-code',
        title: 'C#/.NET',
        text: 'Avec mes connaissances en C# avec les différents frameworks .NET, je sais construire des applications systèmes que ce soit server-side ou client-side. ' +
            'J\'utilise notamment les derniers concepts en terme de développement Windows avec les frameworks WinUI, UWP et WPF.',
        color: 'text-indigo-700'
      },
      {
        icon: 'fa-brands fa-linux',
        title: 'Linux',
        text: 'Ayant beaucoup travaillé sous Linux, je sais utiliser les principales fonctions d\'administration et de gestion',
        color: 'text-teal-600'
      },
      {
        icon: 'fa-brands fa-git-alt',
        title: 'Git',
        text: 'J\'utilise Git pour tous mes projets de développement afin de versionner et gérer mes codes et ressources pour tous vos projets',
        color: 'text-orange-400'
      },
      {
        icon: 'fa-brands fa-docker',
        title: 'Docker',
        text: 'Offrez-vous des micro-services et des services serverless en containerisant vos applications afin de les déployer facilement sur toutes vos ' +
            'machines de production',
        color: 'text-blue-500'
      }
    ]

    const photo = ref()

    const photoText = ref()

    const isPhotoVisible = useElementVisibility(photo)

    const variants: MotionVariants = {
      initial: {
        opacity: 0,
        x: -50
      },
      final: {
        opacity: 1,
        x: 0
      }
    }

    const motion = useMotion(photoText, variants)

    watch(isPhotoVisible, () => {
      if(!isPhotoVisible.value) {
        motion.variant.value = 'final'
      }
      else {
        motion.variant.value = 'initial'
      }
    })

    return {
      y,
      skills,
      photo,
      photoText
    }
  }
})
</script>