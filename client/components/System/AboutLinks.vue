<template>
  <v-list>
    <v-list-item-group>
      <v-list-item
        v-for="linkItem in linkItems"
        :key="linkItem.name"
        rel="noreferrer noopener"
        :href="linkItem.link"
        target="_blank"
      >
        <v-list-item-avatar>
          <v-icon v-text="linkItem.icon" />
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title v-text="linkItem.name" />
        </v-list-item-content>
        <v-list-item-action>
          <v-icon>mdi-open-in-new</v-icon>
        </v-list-item-action>
      </v-list-item>
    </v-list-item-group>
  </v-list>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  data() {
    return {
      linkItems: [
        {
          icon: 'mdi-rocket-launch',
          name: this.$t('links.poweredByJellyfin'),
          link: 'https://jellyfin.org'
        },
        {
          icon: 'mdi-book',
          name: this.$t('links.readTheDocumentation'),
          link: 'https://docs.jellyfin.org'
        },
        {
          icon: 'mdi-translate',
          name: this.$t('links.helpTranslate'),
          link: 'https://translate.jellyfin.org'
        },
        {
          icon: 'mdi-bug',
          name: this.$t('links.reportAnIssue'),
          link: 'https://github.com/jellyfin/jellyfin-vue/issues/new'
        }
      ]
    };
  }
});
</script>
