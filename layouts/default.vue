<template>
  <div>
    <header
      class="
        flex-none
        relative
        z-50
        text-sm
        leading-6
        font-medium
        ring-1 ring-gray-900 ring-opacity-5
        shadow-sm
        py-5
        bg-white
      "
    >
      <nav
        aria-label="Global"
        class="max-w-screen-lg mx-auto px-4 sm:px-6 lg:px-8"
      >
        <div class="flex items-center flex-wrap sm:flex-nowrap">
          <NuxtLink to="/" class="flex-none text-gray-900">
            <span class="text-lg">Alain's Blog</span>
          </NuxtLink>
          <p
            class="
              hidden
              lg:block
              text-sm text-gray-600
              font-normal
              xl:border-l xl:border-gray-200
              ml-3
              xl:ml-4 xl:pl-4 xl:py-0.5
            "
          >
            <span class="hidden xl:inline">Thoughts, ideas, discoveries</span>
          </p>
          <div
            class="
              w-full
              flex-none
              mt-4
              sm:mt-0 sm:w-auto sm:ml-auto
              flex
              items-center
            "
          >
            <Nuxt-Link
              to="articles"
              class="mr-6 sm:mr-0 sm:ml-6 hover:text-gray-900"
              >Articles</Nuxt-Link
            >
            <a
              href="https://www.alainhorner.ch"
              class="mr-6 sm:mr-0 sm:ml-6 hover:text-gray-900"
              >About</a
            >
            <a
              href="https://www.alainhorner.ch"
              class="mr-6 sm:mr-0 sm:ml-6 hover:text-gray-900"
              >Contact</a
            >
          </div>
        </div>
      </nav>
    </header>

    <main class="flex-auto">
      <div class="overflow-hidden">
        <div
          class="max-w-screen-lg mx-auto px-4 sm:px-6 lg:px-8 py-10 md:py-20"
        >
          <Nuxt />
        </div>
      </div>
    </main>

    <footer
      class="
        flex-none
        relative
        text-sm
        leading-6
        font-medium
        ring-1 ring-gray-900 ring-opacity-5
        shadow-sm
        py-5
        bg-black
        text-white
      "
    >
      <div
        class="flex justify-end max-w-screen-lg mx-auto px-4 sm:px-6 lg:px-8"
      >
        <span>
          This is on
          <a href="https://github.com/elHornair/blog" class="text-blue-200"
            >Github
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 20 20"
              class="inline-block fill-current w-6 h-6 -mt-1 ml-1"
            >
              <title>GitHub</title>
              <path
                d="M10 0a10 10 0 0 0-3.16 19.49c.5.1.68-.22.68-.48l-.01-1.7c-2.78.6-3.37-1.34-3.37-1.34-.46-1.16-1.11-1.47-1.11-1.47-.9-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.9 1.52 2.34 1.08 2.91.83.1-.65.35-1.09.63-1.34-2.22-.25-4.55-1.11-4.55-4.94 0-1.1.39-1.99 1.03-2.69a3.6 3.6 0 0 1 .1-2.64s.84-.27 2.75 1.02a9.58 9.58 0 0 1 5 0c1.91-1.3 2.75-1.02 2.75-1.02.55 1.37.2 2.4.1 2.64.64.7 1.03 1.6 1.03 2.69 0 3.84-2.34 4.68-4.57 4.93.36.31.68.92.68 1.85l-.01 2.75c0 .26.18.58.69.48A10 10 0 0 0 10 0"
              ></path>
            </svg>
          </a>
        </span>
      </div>
    </footer>
  </div>
</template>
