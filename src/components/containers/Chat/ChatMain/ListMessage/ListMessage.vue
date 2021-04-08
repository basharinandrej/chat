<template>

    <ul class="list-messages">
        <ListMessageItem 
            v-for="(item, i) in messages"
            :key="i"
            :message="item"
            :currentUserId="currentUserId"
            :currentDialog="currentDialog"
        />
    </ul>

</template>

<script>

import ListMessageItem from '@/components/containers/Chat/ChatMain/ListMessage/ListMessageItem/ListMessageItem.vue'

export default {
    name: 'ListMessage',
    components: {ListMessageItem},
    props: {
        messages: Array,
        currentUserId: Number,
        currentDialog: Object
    }
}

</script>

<style lang="sass">

.list-messages
    background: #fff
    padding: 4px 8px 
    display: flex
    flex-direction: column-reverse
    align-items: flex-end


</style>