<template>
  <q-page class="flex column">
    <div class="col q-pt-lg q-px-md-">
      <q-input
          v-model="search"
          label="Search"
          dark
          placeholder="Search"
      >
        <template v-slot:before>
          <q-icon name="my_location" />
        </template>

        <template v-slot:append>
          <q-btn round dense flat icon="add" />
        </template>
      </q-input>
    </div>

    <template v-if='weatherData'>
      <div class="col text-white text-center">
        <div class="text-h4 text-weight-light">
          Kyiv
        </div>
        <div class="text-h6 text-weight-light">
          Rain
        </div>
        <div class="text-h1 text-weight-thin q-my-lg relative-position">
          <span>8</span>
          <span class="text-h4 relative-position degree">&deg;</span>
        </div>
      </div>
    </template>

    <template v-else>
      <div class="col column text-center text-white">
        <div class="col text-h2 text-weight-thin">
          Quasar <br> Weather
        </div>
        <q-btn class="col" flat>
          <q-icon left size="3em" name="my_location"  />
          <div>Find my Location</div>
        </q-btn>
      </div>
    </template>

  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data() {
    return {
      search: '',
      weatherData: null
    }
  }
}
</script>

<style lang="scss">

  .q-page {
    background: linear-gradient(to bottom, #136a8a, #267871);
  }

  .degree {
    top: -44px
  }
</style>
