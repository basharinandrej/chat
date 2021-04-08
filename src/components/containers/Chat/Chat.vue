<template>

    <div class="chat">
        <ChatAside
            @onCurrentDialog="getCurrentDialogHandler"
            :users="users"
        />
        <ChatMain 
            :currentDialog="this.currentDialog"
            :totalUsers="this.getTotalUsers"
            :currentUserId="currentUserId"
        />
    </div>

</template>

<script>

import ChatAside from '@/components/containers/Chat/ChatAside/ChatAside.vue'
import ChatMain from '@/components/containers/Chat/ChatMain/ChatMain.vue'

export default {
    name: 'Chat',
    components: { ChatAside, ChatMain },
    props: {
        currentUserId: Number
    },
    data() {
        return {
            users: [],
            currentDialog: null
        }
    },
    created() {
        window.onstorage = e => (
            this.users = JSON.parse( e.storageArea.users ).filter(el => el.id !== this.currentUserId)
        )
        this.users = JSON.parse(localStorage.getItem('users')).filter(el => el.id !== this.currentUserId)
    },
    methods: {
        getCurrentDialogHandler(user) {
            this.currentDialog = user
        }
    },
    computed: {
        getTotalUsers() {
            return this.users.length
        }
    }
}
</script>

<style lang="sass">

.chat 
    display: flex
</style>