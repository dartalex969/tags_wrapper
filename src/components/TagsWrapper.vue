<template>
  <div class="d-flex flex-wrap overflow-hidden tags"
       :class="[(align === 'center') ? 'justify-center' : '']"
  >
    <div v-for="tag in tags" :key="tag.title" class="d-flex tag__wrapper">
      <v-icon  x-small
               color="black"
               v-if="tags.indexOf(tag)"
               class="tag__wrapper_separator px-2"
      >
        mdi-circle
      </v-icon>
      <div class="px-2 py-1">
        <v-icon v-if="tag.icon"
                class="px-1 tag__wrapper_icon"
                color="grey"
        >
          {{ 'mdi-' + tag.icon }}
        </v-icon>
        <span class="grey--text font-weight-light title tag__wrapper_title">
          {{ tag.title }}
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TagsWrapper",
  props: {
    tags: {
      type: Array,
      required: true
    },
    align: {
      type: String,
      validator(value) {
        return ['left', 'center'].includes(value)
      },
      default: 'center'
    }
  }
}
</script>

<style scoped lang="scss">
@import "@/assets/styles/style.scss";
</style>