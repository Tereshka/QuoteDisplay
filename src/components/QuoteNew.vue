<template>
    <form class="my-4">
        <div class="form-group">
            <label for="textarea">Quote</label>
            <textarea class="form-control" rows="3" v-model="quote" id="textarea"></textarea>
        </div>
        <button @click.prevent="createNewQuote" class="btn btn-primary">Add new quote</button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                quote: ''
            };
        },
        methods: {
            createNewQuote(){
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>