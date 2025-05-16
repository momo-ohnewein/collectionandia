<template>
    <div class="layout1">
    <ClientOnly>
      <div class="pr-5 z-100">
        <Drawer />
      </div>
      <div class="container">
        <h1 class="text-3xl md:text-3xl lg:text-6xl lg:mb-10 font-bold montserrat-bold">{{ data.title }}</h1>
        <p class="text-lg md:text-2xl lg:text-xl pb-10 font-bold montserrat-semibold">{{ data.description }}</p>

        <div class="roboto-thin">
        <ContentRenderer :value="data" />
        </div>

        <div v-if="data.imagegallery && data.imagegallery.showgallery == true" class="pt-10 pb-20">
            <ImageGallery />
        </div>

        <div class="text-xs leading-3 container">
          <hr>
          <p class="text-xs opacity-50 hover:opacity-100 pb-5">Last update: {{ formatDate(data.date) }}</p>
          
        </div>
      </div>
      <ShareButtons />
    
    </ClientOnly>
    </div>
  </template>
  
  <script setup>
  defineProps(['data', 'formatDate']);
  </script>
  