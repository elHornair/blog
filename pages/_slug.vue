<template>
  <div>
    <NuxtLink to="/"> Go home </NuxtLink>
    <article>
      <h1>{{ article.title }}</h1>
      <p>Created at: {{ formatDate(article.createdAt) }}</p>
      <p>Updated at: {{ formatDate(article.updatedAt) }}</p>
      <nuxt-content :document="article" />
    </article>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const slugParam = params.slug

    if (!slugParam) {
      // TODO: show 404 page
      console.error('oops, 404')
    }

    const queryRes = await $content('articles')
      .where({ slug: slugParam })
      .limit(1)
      .fetch()

    return {
      article: queryRes[0],
    }
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
