<template>
    <div class="auth">
        <h2 class="auth__title">Введите Ваше имя</h2>
        <Form 
            placeholder="Андрей"
            @onFormData="this.setFormDataHandler"
        />
    </div>
</template>

<script>

import Form from '@/components/containers/Form/Form.vue'

export default {
    name: 'Auth',
    components: {Form},
    data() {
        return {
            formData: {},
            users: []
        }
    },
    methods: {
        setFormDataHandler(val) {
            this.formData = val
            this.emitFormDataHandler()
            this.getUsersLocalStorage()
            this.saveUsersLocalStorage(this.formData.value)
        },
        emitFormDataHandler() {
            this.$emit('onFormData', this.formData)
        },
        emitCurrentUser() {
            this.$emit('onCurrentUser', this.users[this.users.length - 1])
        },
        getUsersLocalStorage() {
            this.users = JSON.parse( window.localStorage.getItem('users') ) || []
        },
        saveUsersLocalStorage(items) {
            const objUsers = {
                id: Date.now(),
                name: items
            }
            this.users.push(objUsers)
            window.localStorage.setItem('users', JSON.stringify(this.users))
            this.emitCurrentUser()
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