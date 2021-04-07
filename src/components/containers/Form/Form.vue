<template>

    <form class="main-form" @submit.prevent>

        <TextArea
            placeholder="Введите Сообщение"
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
    components: {Button, TextArea}
}
</script>

<style lang="sass">

.main-form
    display: flex

</style>