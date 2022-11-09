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
$xs: 600px;
$sm: 960px;
$md: 1280px;
$lg: 1920px;

.title {
  vertical-align: middle;
}
.tags {
  height: 40px;
}
.tag__wrapper {
  height: 40px;
}

.tag__wrapper_title {
  @media screen and (max-width: $xs) {
    font-size: 12px !important;
  }
  @media screen and (min-width: $xs) {
    font-size: 14px !important;
  }
  @media screen and (min-width: $sm) {
    font-size: 16px !important;
  }
  @media screen and (min-width: $md) {
    font-size: 22px !important;
  }
  @media screen and (min-width: $lg) {
    font-size: 26px !important;
  }
}

.tag__wrapper_icon {
  @media screen and (max-width: $xs) {
    font-size: 14px !important;
  }
  @media screen and (min-width: $xs) {
    font-size: 16px !important;
  }
  @media screen and (min-width: $sm) {
    font-size: 18px !important;
  }
  @media screen and (min-width: $md) {
    font-size: 24px !important;
  }
  @media screen and (min-width: $lg) {
    font-size: 28px !important;
  }
}

.tag__wrapper_separator {
  @media screen and (max-width: $xs) {
    font-size: 8px !important;
  }
  @media screen and (min-width: $xs) {
    font-size: 8px !important;
  }
  @media screen and (min-width: $sm) {
    font-size: 10px !important;
  }
  @media screen and (min-width: $md) {
    font-size: 12px !important;
  }
  @media screen and (min-width: $lg) {
    font-size: 14px !important;
  }
}
</style>