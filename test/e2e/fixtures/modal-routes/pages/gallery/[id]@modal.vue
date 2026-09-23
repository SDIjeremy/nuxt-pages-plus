<script setup lang="ts">
const router = useRouter()
const id = computed(() => Number.parseInt(router.currentRoute.value.params.id as string) || 1)

function pushNext() {
  useModalRouter().push(`/gallery/${id.value + 1}`)
}
</script>

<template>
  <div class="modal-wrapper">
    <h2>gallery modal {{ id }}</h2>

    <button @click="pushNext">
      Push next
    </button>

    <PlusModalLink open :to="`/gallery/${id + 1}`">
      Open next stack
    </PlusModalLink>

    <PlusModalLink replace to="/gallery/9">
      Replace with last
    </PlusModalLink>

    <NuxtLink to="/">
      Go to index page
    </NuxtLink>

    <button @click="$modalRouter.close()">
      Close
    </button>

    <button @click="$modalRouter.close(true)">
      Close all
    </button>
  </div>
</template>
