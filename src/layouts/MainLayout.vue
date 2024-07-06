<template>
  <q-layout view="hHh lpR fFf">
    <ProfileHeader />
    <ShotGallery />
    <ShotItem />
    <Footer />
  </q-layout>
</template>

<script setup>
import ProfileHeader from "src/components/ProfileHeader.vue";
import ShotGallery from "src/components/ShotGallery.vue";
import ShotItem from "src/components/ShotItem.vue";
import Footer from "src/components/MainFooter.vue";
</script>
