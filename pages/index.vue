<script steup>
import { useUserStore } from '~/stores/user'
const userStore = useUserStore()
</script>

<template>
  <div id="IndexPage" class="w-full overflow-auto">
    <div class="mx-auto max-w-[500px] overflow-hidden">
      <div id="Posts" class="px-4 max-w-[600px] mx-auto">
        <div v-if="isPosts" v-for="post in posts" :key="post">
          {{ post }}
        </div>
      </div>
    </div>
  </div>
</template>