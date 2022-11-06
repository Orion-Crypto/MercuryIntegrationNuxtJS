<script>
import Vue from 'vue'
import { MercuryChat } from '@mercury-chat/vue-chat-previous';
import Tutorial from '~/components/Tutorial.vue';

export default Vue.extend({
  name: 'IndexPage',
  components: {
    MercuryChat,
    Tutorial
}
})
</script>

<template>
  <div>
    <Tutorial />
    <client-only>
      <MercuryChat />
    </client-only>    
  </div>
</template>