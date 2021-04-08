<template>

    <aside class="chat-aside">
        <h2 class="chat-aside__title">Диалоги</h2>

        <ListDialogs 
            @onCurrentDialog="getCurrentDialogHandler"
            :users="users"
        />
    </aside>

</template>

<script>

import ListDialogs from '@/components/containers/Chat/ChatAside/ListDialogs/ListDialogs.vue'

export default {
    name: 'ChatAside',
    components: { ListDialogs },
    props: {
        users: Array
    },
    methods: {
        getCurrentDialogHandler(user) {
            this.$emit('onCurrentDialog', user)
        }
    }
}
</script>

<style lang="sass">

.chat-aside
    width: 30%
    background: #d8ffcf
    padding: 24px 12px
    &__title
        color: #000
        font-size: 18px
        font-family: 'Arial', sans-serif
        font-weight: 100
        margin-bottom: 36px
    &__list-dialogs
        max-height: 290px
        overflow-y: auto

</style>