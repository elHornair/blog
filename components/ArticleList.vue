<template>
  <div>
    <h2
      class="
        text-sm
        font-semibold
        text-blue-800
        uppercase
        tracking-wide
        mb-2
        mt-10
        md:mt-20
      "
    >
      {{ title }}
    </h2>
    <ol>
      <li v-for="article in articles" :key="article.slug" class="mt-5 sm:mt-8">
        <p class="text-sm text-gray-600">
          {{ formatDate(article.publishedAt) }}
        </p>
        <NuxtLink :to="{ name: 'slug', params: { slug: article.slug } }">
          <h3
            class="
              text-2xl
              leading-8
              font-extrabold
              tracking-tight
              text-gray-900
              sm:text-3xl
              mt-1
            "
          >
            {{ article.fullTitle }}
          </h3>
        </NuxtLink>
        <p class="mt-2 text-base text-gray-800">{{ article.summary }}</p>
        <NuxtLink
          :to="{ name: 'slug', params: { slug: article.slug } }"
          class="mt-2 content-link"
        >
          Read more
        </NuxtLink>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'ArticleList',
  props: {
    title: {
      type: String,
      default: '',
    },
    articles: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    formatDate(date) {
      return new Date(date).toLocaleDateString('en', {
        year: 'numeric',
        month: 'short',
        day: 'numeric',
      })
    },
  },
}
</script>
