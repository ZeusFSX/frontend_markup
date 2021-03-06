<template>
  <div>
    <router-link to="/">home </router-link>
    <div>
        <input type="radio" name="ner" id="1" value="PER" v-model="instrument">
        <label for="1">Person</label>
        <input type="radio" name="ner" id="2" value="LOC" v-model="instrument">
        <label for="2">Location</label>
        <input type="radio" name="ner" id="3" value="ORG" v-model="instrument">
        <label for="3">Organization</label>
        <input type="radio" name="ner" id="4" value="DATE" v-model="instrument">
        <label for="4">Date</label>
        <input type="radio" name="ner" id="5" value="NAT" v-model="instrument">
        <label for="5">Nationality</label>
        <input type="radio" name="ner" id="6" value="TITLE" v-model="instrument">
        <label for="6">Title</label>
    </div>
    <hr>
    <ArticleList
      v-bind:articles="articles" v-bind:current_article="current_article"
    />
  </div>
</template>

<script>
import ArticleList from '@/components/ArticleList'


export default {
  name: 'App',
  data () {
    return {
      articles: [
        {id: 1, title: "test 1", text: "Microsoft buy smth", language: "en", tonality: "neutral" },
        {id: 2, title: "test 2", text: "Oracle buy smth", language: "en", tonality: "neutral" },
        {id: 3, title: "test 3", text: "Samsung buy smth", language: "en", tonality: "neutral" }
      ],
      instrument: "PER",
      current_article: 0
    }
  },
  components: {
    ArticleList
  },
  watch: {
      instrument(value) {
          console.log(value)
      }
  }
}
</script>