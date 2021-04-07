<template>

    <li class="list-messages__item">{{ message }}</li>

</template>

<script>

export default {
    name: 'ListMessageItem',
    props: {
        message: String
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


</style>