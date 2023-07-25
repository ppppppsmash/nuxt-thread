<script setup lang="ts">
//import { Post } from '@/types'
import { useUserStore } from '@/stores/user'

interface Post {
  name: string
  image: string
  text: string
  picture: string
}

const userStore = useUserStore()

console.log(userStore)

let posts = ref<Post[]>([])
const isPosts = ref<boolean>(true)
const isLoading = ref<boolean>(false)

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
        <div class="text-white" v-if="isPosts" v-for="(post, index) in posts" :key="index">
          <Post
            :post="post"
            @isDeleted="posts = []"
          />
        </div>
      </div>
    </div>
  </div>
</template>