<template>
    <div class="row">
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
            <lable>Quote</lable>
            <textarea class="form-control" rows="3" v-model="quote"></textarea>
        </div>
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
            <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "NewQuote",
        data: function () {
            return {
                quote: ''
            }
        },
        methods: {
            createNew() {
                if(!this.quote) {
                    return alert('Please enter quote!');
                }
                this.$emit('quoteAdded', this.quote);
                this.quote = '';
            }
        }
    }
</script>

<style scoped>

</style>