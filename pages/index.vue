<template>
  <div>
     <h2>Something new</h2>
      <div v-for="home in homes" :key="home.objectID" style="float:left;margin:10px">
        <nuxt-link :to="`/home/${home.objectID}`"><home-card :home="home"/> </nuxt-link>
      </div>
  </div>
</template>

<script>
import homes from '~/data/homes';

export default {

  data() {
    return {
      homes:homes.slice(0,3)
    }
  }
}
</script>
