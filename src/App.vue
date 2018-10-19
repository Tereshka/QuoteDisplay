<template>
    <div class="container">
        <ProgressBar :quoteCount="quotes.length" :maxQuotes="maxQuotes"/>
        <QuoteNew @quoteAdded="addQuote"/>
        <QuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"/>
        <AlertMessage />
    </div>
</template>

<script>
    import ProgressBar from './components/ProgressBar.vue';
    import QuoteNew from './components/QuoteNew.vue';
    import QuoteGrid from './components/QuoteGrid.vue';
    import AlertMessage from './components/AlertMessage.vue';

    export default {
        data() {
            return {
                quotes: ['First test quote'],
                maxQuotes: 10
            };
        },
        components: {
            QuoteGrid, QuoteNew, AlertMessage, ProgressBar
        },
        methods: {
            addQuote(quote){
                if(this.quotes.length >= this.maxQuotes) {
                    return alert('Please, delete Quotes first!');
                }
                if(quote.length == 0){
                    return alert('Please, fill text of Quote.');
                }
                this.quotes.push(quote);
            },
            deleteQuote(index){
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>
</style>
