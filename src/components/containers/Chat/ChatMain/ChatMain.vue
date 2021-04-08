<template>

    <main class="chat-main">
        <div v-if="currentDialog" class="chat-main__wrapper">
            <h2 class="chat-main__title">
                {{currentDialog.name}}
            </h2>
            <hr>

            <ListMessage
                :messages="messages"
                :currentUserId="currentUserId"
                :currentDialog="currentDialog"
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
            >Добавьте пользователя. Для этого продублируйте вкладку в браузере</p>
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
        totalUsers: Number,
        currentUserId: Number
    },
    data() {
        return {
            messages: []
        }
    },
    updated() {
        window.onstorage = e => (
            this.messages = JSON.parse( e.storageArea.messages )
        )
    },
    methods: {
        getFormDataHandler( objMessage ) {
            this.saveLocalStorageCurrentDialog( objMessage.value )
        },
        getMessagesLocalStorage() { 
            this.messages = JSON.parse( window.localStorage.getItem('messages') ) || []
        },
        saveLocalStorageCurrentDialog( message ) {
            this.getMessagesLocalStorage()
            // TODO Подумать как сделать формирование объекта
            const newMessage = {
                'senderId':  this.currentUserId,
                'messageInfo': {
                    'toAddresseeId': this.currentDialog.id,
                    'textMessage': message
                }
            }
            const messages = this.messages
            messages.unshift(newMessage)
            
            window.localStorage.setItem('messages', JSON.stringify( messages ))
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