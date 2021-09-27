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
      <span class="block xl:inline">{{ article.title }}</span>
      <span class="block text-blue-800 xl:inline">{{ article.title2 }}</span>
    </h1>

    <p
      class="
        mt-3
        text-base text-gray-600
        sm:mt-5 sm:text-lg sm:mx-auto
        md:mt-5 md:text-xl
        lg:mx-0
      "
    >
      {{ formatDate(article.createdAt) }}
    </p>
    <nuxt-content
      :document="article"
      class="prose lg:prose-lg mt-10 sm:mt-18"
    />
  </article>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    const slugParam = params.slug

    if (!slugParam) {
      error({ statusCode: 404, message: 'Post not found' })
    }

    const queryRes = await $content('articles')
      .where({ slug: slugParam })
      .limit(1)
      .fetch()

    if (queryRes.length < 1) {
      error({ statusCode: 404, message: 'Post not found' })
    }

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
