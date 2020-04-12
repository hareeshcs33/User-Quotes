<template>
    <div>
        <div class="progress w-100">
            <div class="progress-bar" 
            v-bind:style="{ width: (QuotesValues.length / maxQuotes) * 100 + '%' }"
            >
                {{(QuotesValues.length/maxQuotes)*100}}
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: [
        "maxQuotes",
        "QuotesValues"
    ],
}
</script>