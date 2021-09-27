<template>
  <div>
    <h2
      class="
        text-sm
        font-semibold
        text-blue-600
        uppercase
        tracking-wide
        mb-2
        mt-10
        md:mt-20
      "
    >
      Latest articles
    </h2>
    <ol>
      <li v-for="article in articles" :key="article.slug" class="mt-6">
        <h3
          class="
            mt-5
            sm:mt-8
            text-2xl
            leading-8
            font-extrabold
            tracking-tight
            text-gray-900
            sm:text-3xl
          "
        >
          {{ article.title }}
        </h3>
        <nuxt-content
          :document="{ body: article.excerpt }"
          class="mt-2 text-md text-gray-800"
        />

        <NuxtLink
          :to="{ name: 'slug', params: { slug: article.slug } }"
          class="
            inline-block
            mt-2
            text-blue-600
            font-medium
            text-md
            hover:text-blue-500
          "
        >
          Read more
        </NuxtLink>
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: 'LatestArticles',
  props: {
    articles: Array,
  },
}
</script>
