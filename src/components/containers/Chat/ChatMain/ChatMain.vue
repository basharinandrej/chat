<template>

    <main class="chat-main">
        <h2 class="chat-main__title">Башарин Андрей</h2>
        <hr>
        <Form />
    </main>

</template>

<script> 

import Form from '@/components/containers/Form/Form.vue'

export default {
    name: 'ChatMain',
    components: {Form}
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
</style>