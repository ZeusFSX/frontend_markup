<template>
    <div>
        <h3>{{article.title}}</h3>
        <ArticleText v-bind:text="article.text" />
        <p>{{article.language}}</p>
        <p>{{article.tonality}}</p>
    </div>   
</template>

<script>
import ArticleText from '@/components/ArticleText'

export default {
    props: {
        article: {
            type: Object,
            required: true
        }
    },
    components: {
        ArticleText
    }
}
</script>

<style scoped>

</style>