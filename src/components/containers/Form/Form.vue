<template>

    <form class="main-form" @submit.prevent="onSubmitHandler">

        <TextArea
            :placeholder="placeholder"
            @onValue="this.setValueTextAreaHandler"
            @onResetValue="this.onResetValueHandler"
        />
        <Button 
            typeAttr="submit"
        >
            Отправить
        </Button>

    </form>

</template>

<script>

import Button from '@/components/commands/Button/Button.vue'
import TextArea from '@/components/commands/TextArea/TextArea.vue'

export default {
    name: 'Form',
    props: {
        placeholder: String
    },
    data() {
        return {
            textAreaValue: ''
        }
    },
    components: { Button, TextArea },
    methods: {
        setValueTextAreaHandler(val) {
            this.textAreaValue = val
        },
        onResetValueHandler(onResetValue) {
            onResetValue && onResetValue()
        },
        onSubmitHandler() {
            const formData = { 
                value: this.textAreaValue
            }
            this.$emit('onFormData', formData)
            this.onResetValueHandler()
        },
    }
}
</script>

<style lang="sass">

.main-form
    display: flex

</style>