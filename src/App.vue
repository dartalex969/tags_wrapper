<template>
  <v-app>
      <tags-wrapper :tags="testTags"
                    align="left"
      />
  </v-app>
</template>

<script>
import TagsWrapper from "@/components/TagsWrapper";

export default {
  name: 'App',

  components: {
    TagsWrapper,
  },

  data() {
    return {
      testTags: [{title: '5', icon: 'star'}, {title: 'Обзорная'}, {title: 'На автобусе', icon: 'bus'},
        {title: '25 марта'}, {title: '6 часов', icon: 'clock'}, {title: 'до 49', icon: 'account'} ]
    }
  }
};
</script>
