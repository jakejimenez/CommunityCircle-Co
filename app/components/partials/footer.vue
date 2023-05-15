<template>
  <footer class="footer -mx-4 md:mx-0">
    <div class="container mx-auto pb-6 flex justify-center">
      <ul class="flex flex-row items-center">
        <li>
          <ul>
            <li
               v-for="(page, index) in pages"
              :key="index"
              class="block font-medium px-4 py-1 md:p-2 lg:px-4">
                <nuxt-link :to="`/${page.slug}`">{{ page.title }}</nuxt-link>
            </li>
            <li>
              <nuxt-link to="/blog" class="block font-medium px-4 py-1 md:p-2 lg:px-4">
               Blog
              </nuxt-link>
            </li>
          </ul>
        </li>
        <li>
          <img :src="logo" style="width: 40%;" alt="Logo" />
        </li>
      </ul>
    </div>
  </footer>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator';
import settings from '@/content/settings/general.json';

@Component
export default class Footer extends Vue {
    get pages(): Page[] {
    return this.$store.state.pages;
  }

  logo = settings.logo;
}
</script>

<style lang="scss">
.footer {
  background-color: $bluise;
}
</style>
