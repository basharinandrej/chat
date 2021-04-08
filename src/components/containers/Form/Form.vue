<template>

    <form class="main-form" @submit.prevent="onSubmitHandler">

        <textarea
            :placeholder="placeholder"
            class="textarea"
            v-model="value"
        ></textarea>
        
        <Button 
            typeAttr="submit"
        >
            Отправить
        </Button>

    </form>

</template>

<script>

import Button from '@/components/commands/Button/Button.vue'

export default {
    name: 'Form',
    props: {
        placeholder: String
    },
    data() {
        return {
            value: ''
        }
    },
    components: { Button },
    methods: {
        onSubmitHandler() {
            const formData = { 
                value: this.value
            }
            this.$emit('onFormData', formData)
            this.value = ''
        },
    }
}
</script>

<style lang="sass">

.main-form
    display: flex

.textarea 
    flex-grow: 1
    padding: 8px 12px
    color: #000
    font-size: 16px
    font-family: sans-serif
    resize: none

</style>