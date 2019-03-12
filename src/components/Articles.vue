<template lang="pug">
  .articles
    .article-item(v-for="article in articles.slice(0, 5)" ,:key="article.id")
      h2 {{ article.title }}
      p {{ article.body }}
</template>
<script>

export default {
  name: 'ArticlesList',
  data() {
    return {
      articles: [],
      articlesUrl: '//jsonplaceholder.typicode.com/posts'
    }
  },
  methods: {
    getArticles() {
      this.$http.get(this.articlesUrl).then(response => {
        this.articles = response.body
      }).catch(e => {
        // eslint-disable-next-line no-console
        console.error(`OK is: ${e.ok}`)
      })
    }
  },
  beforeMount() {
    this.getArticles()
  }
}
</script>
<style lang="scss">
  .articles {
    font: {
      family: sans-serif;
    }
    padding: {
      top: 12px;
    }
  }
  .article-item {
    padding: {
      top: 12px;
      left: 12px;
      right: 12px;
    }
    border: 1px solid gray;
    margin: {
      bottom: 6px;
    }
    h2 {
      margin: 0;
      text: {
        transform: capitalize;
      }
    }
  }
</style>