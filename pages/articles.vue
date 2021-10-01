<template>
  <article>
    <h1
      class="
        text-4xl
        tracking-tight
        font-extrabold
        text-gray-900
        sm:text-5xl
        md:text-6xl
      "
    >
      <span class="block xl:inline">Care to read</span>
      <span class="block text-blue-800 xl:inline">my articles?</span>
    </h1>

    <ArticleList :articles="articles" title="All Articles"></ArticleList>
  </article>
</template>

<script>
export default {
  async asyncData({ $content }) {
    const articles = await $content('articles')
      .where({ draft: { $ne: true } })
      .fetch()

    return {
      articles,
    }
  },
}
</script>
