<template>
  <div class="grey darken-1 empty-layout" id="empty-background" >
    <router-view/>
  </div>
</template>

<script>
import messages from '@/utils/messages'

export default {
  computed: {
    error() {
      return this.$store.getters.error
    }
  },
  watch: {
    error(fbError) {
      this.$error(messages[fbError.code] || 'Что-то пошло не так')
    }
  }
}
</script>
<style scoped>

#empty-background {
  background: url(../imgs/back_login.jpg)
}


</style>


