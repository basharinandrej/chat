<template>

    <main class="chat-main">
        <h2 class="chat-main__title">Башарин Андрей</h2>
        <hr>

        <ListMessage
            :messages="messages"
        />

        <Form 
            placeholder="Введите сообщение"
            @onFormData="this.getFormDataHandler"
        />
    </main>

</template>

<script> 

import Form from '@/components/containers/Form/Form.vue'
import ListMessage from '@/components/containers/Chat/ChatMain/ListMessage/ListMessage.vue'

export default {
    name: 'ChatMain',
    components: {Form, ListMessage},
    data() {
        return {
            messages: []
        }
    },
    methods: {
        getFormDataHandler( obj ) {
            this.messages.unshift(obj.value)
        }
    }
}

</script>

<style lang="sass">

.chat-main
    width: 70%
    background: #b3e6d6
    padding: 24px 12px 0 12px
    display: flex
    flex-direction: column
    &__title
        color: #000
        font-size: 18px
        font-family: 'Arial', sans-serif
        font-weight: 100
    .main-form
        margin-top: auto
        margin-left: -12px
        margin-right: -12px
    .list-messages
        height: 100%
        max-height: 290px
        overflow-y: scroll
</style>