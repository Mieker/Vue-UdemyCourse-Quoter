<template>
<div>
    <h2>Quotes Added</h2>
    <div id="statusBar">
        <div id="progresBar">
            <div id="fillBar">aa</div>
        </div>
    </div>
    <div id="quoteDivWrapper">
        <h5>Quote</h5>
        <textarea v-model="inputedQuote" cols="70" rows="4"></textarea>
        <button id="addButton" class="btn btn-primary" @click="addQuote">Add Quote</button>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            inputedQuote: ''
        }
    },
    methods: {
        addQuote() {
            this.$emit('addQuote', this.inputedQuote);
            this.inputedQuote = '';
        }
    }
}
</script>

<style scoped>
#statusBar {
    width: 100%;
    border: 1px solid grey;
    background-color: lightgrey;
    height: 20px;
    border-radius: 5px;
    margin: auto;
}

#fillBar {
    background-color: cadetblue;
    width: 100%;
    height: 100%;
}

h2 {
    font-weight: 900;
    text-align: left;
}

h5 {
    text-align: left;
}

#addButton {
    display: block;
    margin: auto;
}

textarea {
    width: 100%;
}

#quoteDivWrapper {
    width: 70%;
    margin: auto;
}
</style>
