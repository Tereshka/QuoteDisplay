<template>
    <div class="row" >
        <Quote v-for="(quote, i) in quotes" :key="i" @click.native="deleteQuote(i)">
            <p class="card-text">{{quote}}</p>
        </Quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue'

    export default {
        props: ['quotes'],
        components: {
            Quote
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>