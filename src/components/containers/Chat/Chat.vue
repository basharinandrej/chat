<template>

    <div class="chat">
        <ChatAside />
        <ChatMain />
    </div>

</template>

<script>

import ChatAside from '@/components/containers/Chat/ChatAside/ChatAside.vue'
import ChatMain from '@/components/containers/Chat/ChatMain/ChatMain.vue'

export default {
    name: 'Chat',
    components: { ChatAside, ChatMain }
}
</script>

<style lang="sass">

.chat 
    display: flex
</style>