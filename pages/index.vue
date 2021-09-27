<template>
  <article>
    <h1>{{ page.title }}</h1>
    <nuxt-content :document="page" />
    <LatestArticles :articles="articles"></LatestArticles>
  </article>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const page = await $content('home').fetch()
    const articles = await $content('articles').limit(5).fetch()

    return {
      page,
      articles,
    }
  },
}
</script>
