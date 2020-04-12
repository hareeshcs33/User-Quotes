<template>
    <div>
        <div class="card p-4 my-2">{{item}}</div>
    </div>
</template>
<script>
export default {
    props: [
        "item",
        "index",
    ],
    data(){
        return {
        }
    },
    components: {
    }
}
</script>