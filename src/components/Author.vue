<template>
  <div class="author">
    <h1 v-if="showTitle" class="author__site-title">{{ $static.metaData.siteName }}</h1>

    <p class="author__intro">{{$static.metaData.siteDescription}}</p>

    <p class="author__links">
      <a href="//twitter.com/ianjdarrow">Twitter</a>
      <a href="https://github.com/ianjdarros">GitHub</a>
    </p>
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
		siteDescription
  }
}
</static-query>

<script>
export default {
  props: ["showTitle"]
};
</script>

<style lang="scss">
.author {
  margin: 0 auto;
  max-width: 500px;
  // text-align: center;
  padding-bottom: calc(var(--space) / 2);

  &__image {
    border-radius: 100%;
    width: 90px;
    height: 90px;
    margin-bottom: 1em;
  }

  &__intro {
    opacity: 0.8;
  }

  &__site-title {
    margin: 0 auto;
    font-size: 1.5em;
    // max-width: 400px;
  }

  &__links {
    margin-top: -0.5em;
    a {
      margin-right: 0.5em;
    }
  }
}
</style>
