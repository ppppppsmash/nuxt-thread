<script setup lang="ts">
import { v4 as uuidv4 } from 'uuid'
import { useUserStore } from '@/stores/user'
import { fileURLToPath } from 'url';
const userStore = useUserStore()

// const client = useSupabaseClient()
// const user = useSupabaseUser()

let text = ref(null)
let isLoading = ref(false)

const adjustTextareaHeight = () => {
  const textarea = document.getElementById('textarea')
  textarea.style.height = 'auto'
  textarea.style.height = textarea.scrollHeight + 'px'
}

let file = ref(null)
let fileDisplay = ref(null)
let fileData = ref(null)

const clearData = () => {
  text.value = null
  file.value = null
  fileDisplay.value = null
  fileData.value = null
}

const onChange = () => {
  fileDisplay.value = URL.createObjectURL(file.value.files[0])
  fileData.value = file.value.files[0]
}

</script>

<template>
  <div id="CreatePost" class="fixed z-50 bottom-0 h-full w-full overflow-hidden">

  </div>
</template>