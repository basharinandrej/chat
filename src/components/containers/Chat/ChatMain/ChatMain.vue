<template>

    <main class="chat-main">
        <div v-if="currentDialog" class="chat-main__wrapper">
            <h2 class="chat-main__title">{{currentDialog.name || ''}}</h2>
            <hr>

            <ListMessage
                :messages="messages"
            />

            <Form 
                placeholder="Введите сообщение"
                @onFormData="this.getFormDataHandler"
            />
        </div>
        <p v-else-if="!currentDialog && totalUsers"
            class="chat-main__paragraph">Выберете диалог</p>
        <p v-else
            class="chat-main__paragraph"
            >Добавьте пользователя</p>
    </main>

</template>

<script> 

import Form from '@/components/containers/Form/Form.vue'
import ListMessage from '@/components/containers/Chat/ChatMain/ListMessage/ListMessage.vue'

export default {
    name: 'ChatMain',
    components: {Form, ListMessage},
    props: {
        currentDialog: Object,
        totalUsers: Number
    },
    data() {
        return {
            messages: []
        }
    },
    methods: {
        getFormDataHandler( objMessage ) {
            this.messages.unshift(objMessage.value)
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
    &__wrapper
        height: 100%
        position: relative
    &__title
        color: #000
        font-size: 18px
        font-family: 'Arial', sans-serif
        font-weight: 100
    &__paragraph
        color: #000
        font-size: 14px
        font-family: 'Arial', sans-serif
        font-weight: 100
    .main-form
        position: absolute
        right: 0
        left: 0
        bottom: 0
    .list-messages
        height: 100%
        max-height: 290px
        overflow-y: scroll
</style>