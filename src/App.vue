<template>
<div id="app">
    <appAddQuotePanel @addQuote="addQuote($event)" :quotesNum="quotesNum"></appAddQuotePanel>
    <div v-if="quotes.length > 0">
        <appQuote v-for="quote in this.quotes" v-bind:key="quote" :quote=quote @removeQuote="removeQuote($event)"></appQuote>
    </div>
    <appFooter></appFooter>
</div>
</template>

<script>
import AddQuotePanel from './components/AddQuotePanel';
import Quote from './components/Quote';
import Footer from './components/Footer';

export default {
    components: {
        appAddQuotePanel: AddQuotePanel,
        appQuote: Quote,
        appFooter: Footer,
    },
    data() {
        return {
            quotes: ['Jest dobrze ale nie najgorzej', 'Idziemy na jakoś'],
            quotesNum: 1 /* data of counted quotes */
        }
    },
    methods: {
        removeQuote($event) {
            for (var i = 0; i < this.quotes.length; i++) {
                if (this.quotes[i] === $event) {
                    this.quotes.splice(i, 1);
                }
            }
        },
        addQuote($event) {
            this.quotes.push($event);
        }
    },
    watch: {
        quotes() {
            alert('turu');
            this.quotesNum = this.quotes.length;
            /* issue with counting quotes and printing it on status bar */
        }
    }

}
</script>

<style lang="scss">
#app {
    font-family: 'Helvetica', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin: auto;
    width: 90%;
}

h1,
h2 {
    font-weight: normal;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}
</style>
