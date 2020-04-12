<template>
    <div class="container">
        <div class="my-5">
            <h3 class="text-center">Progress</h3>
            <progress-bar
            :maxQuotes="maxQuotes"
            :QuotesValues="QuotesValues"
            ></progress-bar>
        </div>
        <div class="mb-2">
            <quote-header
                @addQuote="addQuoteToArray"
                ></quote-header>
        </div>
        <div class="mb-2">
            <quote-card
            :QuotesValues="QuotesValues"
            @deleteSingleQuote="deleteSingleQuote"
            ></quote-card>
        </div>
    </div>
</template>
<script>
import ProgressBar from '@/components/progress-bar.vue'
import QuoteCard from '@/components/quote-card.vue'
import QuoteHeader from '@/components/quote-header.vue'
export default {
    data(){
        return {
            maxQuotes: 10,
            QuotesValues: [],
        }
    },
    methods: {
        addQuoteToArray(val) {
            if(this.QuotesValues.length < this.maxQuotes) {
            this.QuotesValues.push(val);
            console.log("val", val);
            } else {
                alert("exceeded max quotes");
            }
        },
        deleteSingleQuote(index){
            this.QuotesValues.splice(index, 1);
            console.log("delete quote..");
        }
    },
    components: {
        ProgressBar,
        QuoteHeader,
        QuoteCard,
    }
}
</script>