<template>
    <p @mouseup="selectedEvent" >{{text}}</p>
</template>

<script>
export default {
    props: {
        article_text: {
            type: String,
            required: true
        }
    },
    data () {
        return {
            text: this.article_text
        }
    },
    methods: {
        selectedEvent: function(){
                const selectedArea = document.getSelection()
                if (!selectedArea.isCollapsed) {
                    let start = selectedArea.anchorOffset;
                    let end = selectedArea.focusOffset;
                    let selectedText = selectedArea.toString();
                    console.log(start, end, selectedText)

                    this.text = this.text.slice(0, start) + "<span v-html=\"html\" >" + selectedText + "</span>" + this.text.slice(end)
                }
                selectedArea.empty()
            }
        
    }
}
</script>

<style scoped>
span {
    background-color: coral;
}
</style>