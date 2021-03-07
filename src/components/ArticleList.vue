<template>
    <div>
        <ArticleItem :article="article" :key="article.id" :instrument="instrument"/>
        <b-button-group>
            <b-button class="m-sm-4" variant="success" v-on:click="save_article">Save Article</b-button>
        </b-button-group>
        <b-button-group>
            <b-button class="m-sm-4" variant="primary" v-on:click="next_article">Next Article</b-button>
        </b-button-group>
    </div>
</template>

<script>
import ArticleItem from '@/components/ArticleItem'


export default {
    props: ['articles', 'current_article', 'instrument'],
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
        save_article: function(){
        }

    }
}
</script>
<style scoped>

</style>