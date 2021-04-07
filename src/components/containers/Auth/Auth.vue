<template>
    <div class="auth">
        <h2 class="auth__title">Введите Ваше имя</h2>
        <Form 
            placeholder="Андрей"
            @onFormData="this.getFormDataHandler"
        />
    </div>
</template>

<script>

import Form from '@/components/containers/Form/Form.vue'

export default {
    name: 'Auth',
    components: {Form},
    methods: {
        getFormDataHandler(val) {
            this.$emit('onFormData', val)
        }
    }
}
</script>

<style lang="sass">

.auth
    padding: 24px 12px
    box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.5)
    background: #ffe09c
    .main-form
        flex-direction: column
    .textarea
        margin-bottom: 32px
    &__title
        color: #000
        font-family: sans-serif
        font-size: 14px
        margin-bottom: 12px

</style>