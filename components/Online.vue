<template>
  <main class="container">
    <img :src="ku" />
    <div
      v-if="posts"
      class="posts">
      <article
        v-for="post in posts.slice(0, 6)"
        :key="post.id"
        class="posts__post post-item">
        <h2 class="post-item__name">{{ post.title }}</h2>
        <p class="post-item__body">{{ post.body }}</p>
      </article>
    </div>
    <div
      v-else
      class="text-center py-8">
      <p class="text-gray-500">Loading data...</p>
    </div>
  </main>
</template>

<script setup>
import ku from "/public/ku.webp";

const props = defineProps({
  online: Boolean,
});

const { data: posts } = await useFetch("/posts", {
  baseURL: useRuntimeConfig().public.apiBase,
  initialCache: false,
});
</script>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;

  &__status {
    display: flex;
    align-items: center;

    &-round {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      margin-right: 5px;
      animation: pulse 1.5s infinite;
    }

    &--online {
      background-color: rgba(green, 0.7);
    }

    &--offline {
      background-color: rgba(red, 0.7);
    }
  }
}

@keyframes pulse {
  0% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.3;
    transform: scale(0.95);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.post {
  &-item {
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 10px;
    margin-bottom: 10px;

    &__name {
      margin-bottom: 0;
      margin-top: 0;
    }

    &__body {
      margin: 0;
      padding: 0;
    }
  }
}

.container {
  width: 100%;
  height: auto;
  padding-bottom: 50px;

  img {
    width: 100%;
    height: auto;
    object-fit: cover;
  }
}
</style>
