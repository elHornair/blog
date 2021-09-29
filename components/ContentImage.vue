<template>
  <figure>
    <img :src="src" :alt="alt" :title="title" />
    <figcaption v-if="title">{{ title }}</figcaption>
  </figure>
</template>

<script>
export default {
  name: 'ContentImage',
  props: {
    src: {
      type: String,
      required: true,
    },
    alt: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
  },
}
</script>
