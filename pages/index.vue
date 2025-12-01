<template>
  <section class="page">
    <div class="mx-auto max-w-6xl grid grid-cols-6 gap-3">
      <div class="col-span-6 md:col-span-4">
        <ImageSlider :images="images"/>
      </div>
      <div class="col-span-6 md:col-span-2">
        <ArticelCard identifier="gzxcvxoljapt577" />
      </div>
      <CatalogProductGrid identifier="action-dvd"/>
    </div>
  </section>
</template>

<script setup lang="ts">
import ImageSlider from "@/components/content/ImageSlider.vue";
import ArticelCard from "~/components/blog/ArticelCard.vue";
import {usePocketBase} from "../utils/pocketbase";

useSeoMeta({
  title: 'Media Store by JMSE - My-Media.world',
  keywords:
      'jmse,media store,store,movies,gummersbach,bergneustadt,my,media,world,my-media.world,my-media,my media,filme,serien,kinofilme',
  description:
      'My Media World, ist meine Welt der Medien gefüttert von TMDB mit Film Daten soll es erstmal zeigen was mit PocketStore.io möglich ist by JMSE.',
})

const images = ref([]);
const pb = usePocketBase();

onMounted(async() => {
  images.value = (await pb.collection('product_pictures').getList(1,10, {
    filter: 'name ~"homepage-%"'
  })).items;
});
</script>