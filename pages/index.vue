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
      <span class="block xl:inline">{{ page.title }}</span>
      <span class="block text-blue-800 xl:inline">{{ page.title2 }}</span>
    </h1>

    <nuxt-content
      class="
        mt-3
        text-base text-gray-500
        sm:mt-5 sm:text-lg sm:mx-auto
        md:mt-5 md:text-xl
        lg:mx-0
      "
      :document="page"
    />
    <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
      <div class="rounded-md shadow">
        <Nuxt-Link
          to="articles"
          class="
            w-full
            flex
            items-center
            justify-center
            py-3
            px-4
            font-semibold
            text-sm
            border border-transparent
            rounded-md
            text-white
            bg-blue-800
            hover:bg-blue-900
            md:py-4 md:text-md md:px-10
          "
        >
          Start Reading
        </Nuxt-Link>
      </div>
      <div class="mt-3 sm:mt-0 sm:ml-3">
        <a
          href="https://www.alainhorner.ch"
          class="
            w-full
            flex
            items-center
            justify-center
            py-3
            px-4
            font-semibold
            text-sm
            border border-transparent
            rounded-md
            text-blue-900
            bg-blue-100
            hover:bg-blue-200
            md:py-4 md:text-md md:px-10
          "
        >
          Get in touch
        </a>
      </div>
    </div>

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
