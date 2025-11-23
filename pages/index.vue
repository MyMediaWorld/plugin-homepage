<template>
  <section class="page">
    <div class="mx-auto max-w-6xl grid grid-cols-6 gap-3">
      <HomepageHero />
      <CatalogProductGrid identifier="action-dvd" />
    </div>
  </section>
</template>

<script setup lang="ts">
import { addBreadcrumb } from "~/utils/breadcrumb";
const { t } = useI18n();
useHead({
    title: 'My-Media.World - ' + t("general.title"),
    meta: [
        {
            name: "description",
            content:
                "Dies ist ein Demo Store von PocketStore.io",
        },
    ],
});

onMounted(() => {
    addBreadcrumb({
        code: "overview",
        link: "/",
        icon: "boxes-stacked",
    });
});
</script>