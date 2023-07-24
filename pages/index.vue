<script steup>
// import { useUserStore } from '~/stores/user'
// const userStore = useUserStore()

let posts = ref([])
const isPosts = ref(true)
const isLoading = ref(false)

posts.value = [
  {
    name: 'ARATA',
    image: 'https://placehold.co/100',
    text: 'This is the title',
    picture: 'https://placehold.co/100',
  }
]
</script>

<template>
  <div id="IndexPage" class="w-full overflow-auto">
    <div class="mx-auto max-w-[500px] overflow-hidden">
      <div id="Posts" class="px-4 max-w-[600px] mx-auto">
        <div class="text-white" v-for="post in posts" :key="post">
          {{ post }}
        </div>
      </div>
    </div>
  </div>
</template>