<template>

    <textarea
        :placeholder="this.placeholder"
        class="textarea"
    ></textarea>

</template>

<script>

export default {
    name: 'TextArea',
    props: {
        placeholder: String
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