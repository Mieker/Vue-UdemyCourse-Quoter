<template>
<div>
    <p @click="removeQuote">"{{ quote }}"</p>
</div>
</template>

<script>
export default {
    props: ['quote'],
    methods: {
        removeQuote() {
            this.$emit('removeQuote', this.quote)
        }
    }

}
</script>

<style scoped>
div {
    border: 1px solid grey;
    border-radius: 5px;
    display: inline-block;
    margin: 10px;
}

p {
    font-style: italic;
    padding: 10px;
    margin: auto;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>
