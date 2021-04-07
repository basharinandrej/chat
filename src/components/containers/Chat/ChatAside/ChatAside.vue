<template>

    <aside class="chat-aside">
        <h2 class="chat-aside__title">Диалоги</h2>

        <ListDialogs 
            :users="this.users"
        />
    </aside>

</template>

<script>

import ListDialogs from '@/components/containers/Chat/ChatAside/ListDialogs/ListDialogs.vue'

export default {
    name: 'ChatAside',
    data() {
        return {
            users: ['Тимур Меллиоранский', 'Иван Демидов', 'Максим Сытов']
        }
    },
    components: { ListDialogs }
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

</style>