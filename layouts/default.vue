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
              text-sm text-gray-500
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
            <Nuxt-Link
              to="about"
              class="mr-6 sm:mr-0 sm:ml-6 hover:text-gray-900"
              >About</Nuxt-Link
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
        <div class="max-w-screen-lg mx-auto px-4 sm:px-6 lg:px-8 py-20">
          <Nuxt />
        </div>
      </div>
    </main>

    <footer>Le footer</footer>
  </div>
</template>
