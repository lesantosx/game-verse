<template>
  <div id="banner" class="flex">
    <img v-if="!isLoading" :src="items[0]" class="h-[320px] w-[700px] rounded-md" draggable="false">
    <USkeleton v-else class="h-[320px] w-[700px]" :class="colorModeClass" />    
    <div>
      <template v-for="item in items">
        <img v-if="!isLoading" :src="item" class="h-[50px] w-[160px] ml-[40px] mb-[40px] rounded-md" draggable="false">
        <USkeleton v-else class="h-[50px] w-[160px] ml-[40px] mb-[40px]" :class="colorModeClass" />        
      </template>      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLoading: true,
      //MOCK
      items: [
        'https://picsum.photos/1920/1080?random=1',
        'https://picsum.photos/1920/1080?random=2',
        'https://picsum.photos/1920/1080?random=3',
        'https://picsum.photos/1920/1080?random=4'
      ]
    }
  },
  computed: {
    colorModeClass() {
      return this.$colorMode.value === 'dark' ? 'bg-gray-800' : 'bg-gray-200'
    }

  }
}
</script>

<style>
#banner {
  margin-left: 60px;
  
  .skeleton-custom {
    margin-left: 20px;
  }
}
</style>