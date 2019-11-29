<template>
  <div>
    <h1>Create an Event, {{ user.name }}</h1>
    <p>This event was created by {{ user.id }}</p>
    <p> The first Event: {{ getEvent(1).title }}</p>
    <p>
      There are {{ catLength }} categories
    </p>
    <ul>
      <li v-for="cat in categories" :key="cat">
        {{ cat }}
      </li>
    </ul>
  </div>
</template>

<script>
import { mapGetters, mapState } from 'vuex';

export default {
  computed: {
    ...mapGetters({
      catLength: 'catLength',
      getEvent: 'getEventById'
    }),
    ...mapState(['user', 'categories', 'events'])
  }
}
</script>

<style>

</style>