This is a [Nuxt.js](https://nuxtjs.org/) project that integrates [Mercury Chat](https://mercurychat.io/), a Cardano wallet communication platform!

This repository serves as an example to showcase how you can embed Mercury Chat into your Cardano DAPP. This example works for both Typescript and Javascript frontends.

<br />

## Integration

To get Mercury Chat in your application, we will need to install the [Mercury Chat Package](https://www.npmjs.com/package/@mercury-chat/vue-chat-previous):

```bash
npm install @mercury-chat/vue-chat-previous
```

<b>Note</b>: You can also use yarn, or pnpm to install the package.

After installation you need to add the Mercury Chat package to your nuxt.config.js file and the plugin folder like this:

nuxt.config.js
```
// Plugins to run before rendering page: https://go.nuxtjs.dev/config-plugins
plugins: [ { src: "~/plugins/mercury-chat", mode: 'client' } ],

// Build Configuration: https://go.nuxtjs.dev/config-build
build: { transpile: ['@mercury-chat/vue-chat-previous'] }
```

plugins/mercury-chat.js
```
import Vue from 'vue';
import MercuryChat from '@mercury-chat/vue-chat-previous';
Vue.use(MercuryChat);
```

After the above you use Mercury Chat in your application like this:

```
<script>
import Vue from 'vue'
import { MercuryChat } from '@mercury-chat/vue-chat-previous';

export default Vue.extend({
  name: 'IndexPage',
  components: {
    MercuryChat 
  }
})
</script>

<template>
  <div>
    <client-only>
      <MercuryChat />
    </client-only>    
  </div>
</template>
```

And we're done! Congratulations you have successfully added Mercury Chat to your Cardano Dapp!

<br />

![NuxtFullscreen](https://user-images.githubusercontent.com/17760631/200148502-f3e19b19-fdf7-4b22-a444-2bacbbbee070.PNG)

<br />

## Options
There are some options allow you to customize the Mercury Chat experience. Below is an example of the options that can be used. The full option documentation can be found in the [Mercury Chat NPM Page](https://www.npmjs.com/package/@mercury-chat/vue-chat-previous)

```
<MercuryChat position='bottom-right' :hasFullscreen='false' :showBackground='false' />
```

<br />

![NuxtSmallScreen](https://user-images.githubusercontent.com/17760631/200148509-cfd9b642-5bce-4574-b12b-bd6fefe56743.PNG)

<br />

## Running This Repository

If you would like to test our the Mercury Chat functionality within this repo, clone the repo and then run the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

And that's it! Play around the ```<MercuryChat />``` component's properties until you have the functionality that you like!
