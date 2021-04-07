<template>

    <textarea
        :placeholder="placeholder"
        class="textarea"
        v-model="value"
        @change="onChangeHandler"
    ></textarea>
 


</template>

<script>

export default {
    name: 'TextArea',
    props: {
        placeholder: String
    },
    data() {
        return {
            value: ''
        }
    },
    methods: {
        getValue() {
            return this.value
        },
        onChangeHandler() {
            this.$emit('onValue', this.getValue())
        }
    }
}
</script>

<style lang="sass">

.textarea 
    flex-grow: 1
    padding: 8px 12px
    color: #000
    font-size: 16px
    font-family: sans-serif
    resize: none

</style>