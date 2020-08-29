<template>
<div>
    <h2>Quotes Added</h2>
    <div id="statusBar">
        <div id="progresBar">
            <div id="fillBar">{{ quotes.length }} / 10</div>
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
    props: ['quotes'],
    data() {
        return {
            inputedQuote: ''
        }
    },
    methods: {
        addQuote() {
            if (this.inputedQuote == '') {
                alert('Your quote is empty!')
            }
            else if (this.quotes.length < 10) {
                this.$emit('addQuote', this.inputedQuote);
                this.inputedQuote = '';
            }
            else {
                alert('The qouotes box is full!')
            }
        }
    }
}
</script>

<style scoped>
#statusBar {
    width: 100%;
    height: 22px;
    border: 1px solid grey;
    background-color: lightgrey;
    border-radius: 5px;
    margin: auto;
    display: inline-block;

}

#fillBar {
    background-color: cadetblue;
    margin: 0;
    padding: 0;
    border-radius: 5px;
    height: 20px;
    font-size: 15px;
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
