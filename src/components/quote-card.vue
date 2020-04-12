<template>
    <div class="row m-0">
        <quote
            v-for="(item, index) in QuotesValues"
            :key="index"
            class="col-4"
            :item="item"
            :index="index"
            @click.native="deleteQuote(index)"
            ></quote>
    </div>
</template>
<script>
import Quote from '@/components/quote.vue';
import EventBus from './event-bus.js';

export default {
    props: [
        "QuotesValues",
    ],
    data(){
        return {
        }
    },
    components: {
        Quote,
    },
    methods: {
        deleteQuote(index) {
            this.$emit('deleteSingleQuote', index);
        //     this.QuotesValues.slice(index, 1);
        //     console.log('delete quote');
        }
    },
    // mounted () {
    //     EventBus.$on('QuoteTextVal', (val) => {
    //         if(this.QuotesValues.length <= this.maxQuotes) {
    //             this.QuotesValues.push(val);
    //         } else {
    //             alert("Quotes exceeded max number");
    //         }
    //     });
    // },
}
</script>