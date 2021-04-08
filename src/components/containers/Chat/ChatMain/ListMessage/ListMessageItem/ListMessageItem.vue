<template>

    <li class="list-messages__item" :class="{'list-messages__item--my': addClassMyMessage}">
        {{message.messageInfo.textMessage}}
    </li>
    
</template>

<script>

export default {
    name: 'ListMessageItem',
    props: {
        message: Object,
        currentUserId: Number,
        currentDialog: Object
    },             
    computed: {
        addClassMyMessage() {
            return this.message.senderId === this.currentUserId
        }
    }       
}

</script>

<style lang="sass">

.list-messages
    &__item
        background: #0f16e6
        list-style: none
        max-width: max-content
        padding: 8px
        border-radius: 8px
        box-shadow: 2px 2px 2px rgba(0, 0, 0, .3)
        color: #fff
        font-size: 16px
        font-family: sans-serif
        margin-bottom: 20px
        &--my
            margin-right: auto
            background: #1ad41a

</style>