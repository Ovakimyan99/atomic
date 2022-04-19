<template>
  <div class="">
    <h2 class="">
      <slot name="title" />
    </h2>
    <p class="">
      <slot name="content" />
    </p>
    <div>
      {{ slot }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'SquareInfo',
  computed: {
    slot () {
      console.log(this.$slots.title)
      return !!this.$slots.title || !!this.$slots.content
    }
  }
}
</script>
