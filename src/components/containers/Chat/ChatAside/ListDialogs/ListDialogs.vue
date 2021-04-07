<template>

    <ul class="chat-aside__list-dialogs list-dialogs">
        <ListDialogsItem 
            v-for="(item, i) in users"
            :key="i"
            :name="item"
        />
    </ul>

</template>

<script>

import ListDialogsItem from '@/components/containers/Chat/ChatAside/ListDialogs/ListDialogsItem/ListDialogsItem.vue'

export default {
    name: 'ListDialogs',
    props: {
        users: Array
    },
    components: {ListDialogsItem}
}
</script>