<template>

    <li class="list-dialogs__item" 
        @click="this.emitHandler">
        {{ item.name }}
    </li>

</template>

<script>

export default {
    name: 'ListDialogsItem',
    props: {
        item: Object
    },
    methods: {
        emitHandler() {
            this.$emit('onCurrentDialog', this.item)
        }
    }
}
</script>

<style lang="sass">
    .list-dialogs
        &__item
            cursor: pointer
            background: #6ff19d
            list-style: none
            padding: 8px 4px
            font-family: 'Arial', sans-serif
            margin-bottom: 8px
            border-radius: 2px
            transition: .3s
            font-size: 16px
            white-space: nowrap
            text-overflow: ellipsis
            overflow: hidden
        &__item:last-child
            margin-bottom: 0
        &__item:hover
            transition: .3s
            box-shadow: 2px 2px 2px rgba(0, 0, 0, .3)

</style>