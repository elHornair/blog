<template>
  <div>
    <h2>Latest articles</h2>
    <ol>
      <li v-for="article in articles" :key="article.slug">
        <NuxtLink :to="{ name: 'slug', params: { slug: article.slug } }">
          <h3>{{ article.title }}</h3>
        </NuxtLink>
        <nuxt-content :document="{ body: article.excerpt }" />
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
