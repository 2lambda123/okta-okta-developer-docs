<template>
  <div
    v-if="showPageTitle"
    class="page-title"
  >
    <h1 class="page-title--title">
      <i
        v-if="$page.frontmatter.icon"
        class="icon-48"
        :class="$page.frontmatter.icon"
      />
      {{ $page.title }}
    </h1>
  </div>
</template>

<script>
  export default {
    name: 'PageTitle',
    computed: {
      showPageTitle() {
        if (this.$page.path.includes("/docs/guides")) {
          return true;
        }
        if (this.$page.frontmatter.generated) {
          return true;
        }
        return this.$page.frontmatter.icon ? true : false;
      }
    }
  }
</script>
