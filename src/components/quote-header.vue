<template>
    <div>
        <div class="form-group">
            <textarea
                type="text"
                placeholder="Enter quote text"
                v-model="QuoteText"
                class="form-control"
                rows="3"
                ></textareatype="text">
        </div>
        <div class="action-block text-center">
            <button class="btn btn-primary cta-300" @click="QuoteSubmit">Submit</button>
        </div>
    </div>
</template>
<script>
import EventBus from './event-bus.js';
export default {
    data(){
        return {
            QuoteText: '',
        }
    },
    methods: {
        // QuoteSubmit(){
        //     console.log('QuoteSubmit');
        //     if(this.QuoteText) {
        //         EventBus.$emit('QuoteTextVal', this.QuoteText);
        //     } else {
        //         alert("No quote text");
        //     }
        // },
        QuoteSubmit(){
            console.log('QuoteSubmit');
            if(this.QuoteText) {
                this.$emit('addQuote', this.QuoteText);
                this.QuoteText = "";
            } else {
                alert("No quote text");
            }
        }
    }
}
</script>