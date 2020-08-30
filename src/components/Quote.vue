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
    cursor: pointer;
}

div:hover {
    background-color: pink;
}

p {
    padding: 10px;
    margin: auto;
    font-family: Tangerine;
    font-size: 35px;
}
</style>
