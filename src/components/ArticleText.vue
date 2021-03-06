<template>
    <p @mouseup="selectedEvent" v-html="text" >{{text}}</p>
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
            text: this.article_text,
            offset: 0
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

                    this.text = this.text.slice(0, start + this.offset) + "<span style=\"background-color: coral;\">" + selectedText + "</span>" + this.text.slice(end + this.offset)
                    this.offset += 46
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