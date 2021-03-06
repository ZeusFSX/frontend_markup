<template>
    <div>
        <ArticleItem :article="article" :key="article.id" />
        <button v-on:click="prev_article">PREV</button>
        <button v-on:click="next_article">NEXT</button>
    </div>
</template>

<script>
import ArticleItem from '@/components/ArticleItem'


export default {
    props: ['articles', 'current_article'],
    components: {
        ArticleItem
    },
    data: function(){
        return {
            article: this.articles[this.current_article],
            current_counter: this.current_article
        }
    },
    methods: {
        next_article: function(){
            this.current_counter += 1
            if (this.current_counter > this.articles.length - 1) {
                this.current_counter= 0
            }
            this.article = this.articles[this.current_counter]
        }, 
        prev_article: function(){
            this.current_counter -= 1
            if (this.current_counter < 0) {
                this.current_counter= this.articles.length - 1
            }
            this.article = this.articles[this.current_counter]
        }

    }
}
</script>
<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>