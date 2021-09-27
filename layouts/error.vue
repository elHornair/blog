<template>
  <div class="flex flex-col sm:flex-row mx-auto max-w-2xl">
    <span class="block font-extrabold text-6xl text-blue-800">{{
      error.statusCode
    }}</span>
    <div class="sm:border-l-2 sm:ml-6 sm:pl-6">
      <div
        class="
          text-4xl
          tracking-tight
          font-extrabold
          text-gray-900
          sm:text-5xl
          md:text-6xl
        "
      >
        <h1 v-if="error.statusCode === 404">Page not found</h1>
        <h1 v-else>Unknown error</h1>
      </div>
      <p
        class="
          my-3
          text-base text-gray-600
          sm:my-5 sm:text-lg sm:mx-auto
          md:my-5 md:text-xl
          lg:mx-0
        "
      >
        Something's not quite right. Change the URL or click one of the buttons
        below.
      </p>
      <div class="rounded-md shadow inline-block">
        <Nuxt-Link
          to="/"
          class="
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
          Go Home
        </Nuxt-Link>
      </div>
      <div class="ml-2 sm:ml-3 sm:mt-0 inline-block">
        <a
          href="https://www.alainhorner.ch"
          class="
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
          Contact me
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: () => {},
    },
  },
}
</script>
