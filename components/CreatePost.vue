<script setup lang="ts">
import { v4 as uuidv4 } from 'uuid'
import { useUserStore } from '@/stores/user'
import { fileURLToPath } from 'url'
const userStore = useUserStore()

// const client = useSupabaseClient()
// const user = useSupabaseUser()

let text = ref(null)
let isLoading = ref(false)

const adjustTextareaHeight = () => {
  const textarea = document.getElementById('textarea')
  textarea?.style?.setProperty('height', 'auto')
  textarea?.style?.setProperty('height', `${textarea?.scrollHeight}px`)
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

const fileInput = document.getElementById('fileInput') as HTMLInputElement;

const onChange = () => {
  if (!fileInput?.files?.[0]) return

  const selectedFile = fileInput.files[0]
  fileDisplay.value = URL.createObjectURL(selectedFile);
  fileData.value = selectedFile;
}

</script>

<template>
  <div id="CreatePost" class="fixed z-50 bottom-0 h-full w-full overflow-hidden">
    <div class="bg-black h-full w-full text-white overflow-auto">
      <div
        class="flex items-center justify-start py-4 max-w-[500px] mx-auto
          border-b border-b-gray-700"
      >
        <button
          class="rounded-full px-2"
          @click="
            userStore.isMenuOverlay = false;
            clearData();
          "
        >
          <Icon name="mdi:close" size="25" />
        </button>
      </div>
    </div>
  </div>
</template>