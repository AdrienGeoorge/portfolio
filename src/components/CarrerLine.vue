<template>
  <div class="grid-carrer">
    <img :src="image" alt="" class="company-logo">
    <div class="job-line">
      <div class="title">
        <slot name="title"></slot>
      </div>
      <slot name="company"></slot>
      <div class="job-date">
        <slot name="date"></slot>
      </div>
      <p class="mt-1">
        <slot></slot>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ['image']
}
</script>
