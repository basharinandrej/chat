<template>

    <ul class="list-messages">
        <ListMessageItem 
            v-for="(item, i) in messages"
            :key="i"
            :message="item"
        />
    </ul>

</template>

<script>

import ListMessageItem from '@/components/containers/Chat/ChatMain/ListMessage/ListMessageItem/ListMessageItem.vue'

export default {
    name: 'ListMessage',
    components: {ListMessageItem},
    props: {
        messages: Array
    },
    data() {
        return {
            text: 'text'
        }
    }
}

</script>

<style lang="sass">

.list-messages
    background: #fff
    padding: 4px 8px 
    display: flex
    flex-direction: column-reverse


</style>