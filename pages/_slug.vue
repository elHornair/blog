<template>
  <div>
    <nav class="mb-8 sm:mb-12 md:mb-16 max-w-2xl mx-auto">
      <NuxtLink to="/" class="content-link"> Home </NuxtLink>
      / <NuxtLink to="articles" class="content-link"> Articles </NuxtLink>
      /
      <span>{{ article.fullTitle }}</span>
    </nav>

    <article>
      <div class="max-w-2xl mx-auto">
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
          <span class="block text-blue-800 xl:inline">{{
            article.title2
          }}</span>
        </h1>
        <p
          class="
            mt-3
            text-base text-gray-600
            sm:mt-5 sm:text-lg sm:mx-auto
            md:text-xl
            lg:mx-0
          "
        >
          {{ article.summary }}
        </p>
        <p
          class="
            mt-3
            mb-4
            text-sm text-gray-600
            sm:mt-5 sm:mb-6 sm:text-base
            lg:mx-0
          "
        >
          {{ formatDate(article.publishedAt) }}
        </p>
      </div>
      <ContentImage
        v-if="article.mainImagePath && article.mainImageAlt"
        :alt="article.mainImageAlt"
        :src="article.mainImagePath"
      ></ContentImage>
      <nuxt-content
        :document="article"
        class="prose md:prose-md lg:prose-lg mt-10 sm:mt-18 max-w-2xl mx-auto"
      />
    </article>
  </div>
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
