<template>

    <button class="btn" :type="typeAttr">
        <slot />
    </button>

</template>

<script>

export default {
    props: {
        typeAttr: String
    }
}
</script>

<style lang="sass">

.btn
    padding: 8px 12px
    border: none
    background: #4c4cdc
    color: #fff
    font-size: 16px
    border-radius: 0
    cursor: pointer
    transition: .3s
    &:hover
        transition: .3s
        background: #3131b5

</style>