<template>
  <div id="app">
    <div class="app-wrapper">

      <div class="container">
        <h1 class="app-wrapper__title">Realtime Chat</h1>

        <Chat />

      </div>

    </div>
  </div>
</template>

<script>

import Chat from '@/components/containers/Chat/Chat.vue'

export default {
  name: 'App',
  components: { Chat }
}
</script>

<style lang="sass">

*
  box-sizing: border-box
  margin: 0
  padding: 0 
  
.app-wrapper 
  display: flex
  height: 100vh
  background: purple
  &__title
    margin-top: 36px
    margin-bottom: 36px
    font-size: 36px
    font-family: 'Arial', sans-serif
    color: #fff
    text-align: center
  .chat
    max-width: 720px
    box-shadow: 2px 2px 2px rgba(0, 0, 0, .5)
    margin: 0 auto
    min-height: 400px

.container
  width: 1170px
  max-width: 100%
  margin: 0 auto

</style>