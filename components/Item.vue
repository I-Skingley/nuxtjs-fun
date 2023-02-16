<template>
    <div class="item">
        <div class="item-pic">

        </div>
        <div class="item-abstract"><p>{{ abstract }}</p></div>
    </div>
</template>

<script>
export default {
    name: 'item',
    props: ['abstract'],
    data() {
        return {
            description: 'An item'
        }
    },
    metaInfo() {
        return {
            abstract: this.abstract,
            meta: [
                {vmid: 'description', name: 'description, content: this.description' }
            ]
        }
    }
}
</script>
