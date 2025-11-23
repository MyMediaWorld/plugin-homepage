<template>
  <section class="page">
    <div class="mx-auto max-w-6xl grid grid-cols-6 gap-3">
      <ImageSlider :images="images"/>
      <CatalogProductGrid identifier="action-dvd"/>
    </div>
  </section>
</template>

<script setup lang="ts">
import ImageSlider from "@/components/content/ImageSlider.vue";

useHead({
  title: 'Media Store by JMSE - My-Media.world',
  meta: [
    {
      name: 'keywords',
      content: 'jmse,media store,store,movies,gummersbach,bergneustadt,my,media,world,my-media.world,my-media,my media,filme,serien,kinofilme'
    },
    {
      name: "description",
      content:
          "My Media World, ist meine Welt der Medien gefüttert von TMDB mit Film Daten soll es erstmal zeigen was mit PocketStore.io möglich ist by JMSE.",
    },
  ],
  script: [{
    async: true,
    src: 'https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-1250525441896834'
  }]
});

const images = [
  {
    media: 'https://image.tmdb.org/t/p/original/6U17IFhOo7omnuD2mrFQIaHx82B.jpg'
  },
  {
    media: 'https://image.tmdb.org/t/p/original/ah3m5E28pE4vsFnNvoTTdVxxT3B.jpg'
  },
  {
    media: 'https://image.tmdb.org/t/p/original/ebg8TF2vYaSVNVLv8WO8omebrjw.jpg'
  }
]

onMounted(() => {
  nextTick(() => {
    console.log('tick: ', window.adsbygoogle);
    if (window.adsbygoogle) {
      window.adsbygoogle.push({});
    }
  })
});
</script>