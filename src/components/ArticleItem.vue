<template>
    <div>
        <h3>{{article.title}}</h3>
        <p>{{article.text}}</p>
        <p>{{article.language}}</p>
        <p>{{article.tonality}}</p>
    </div>   
</template>

<script>
export default {
    props: {
        article: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>

</style>