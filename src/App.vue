<template>
  <div id="app">
    <!-- Using value -->
    <b-button v-b-modal="'comp'">Show Apartment Complexes</b-button>

    <hr>

    <b-list-group v-if="complexSelected.length > 0">
      <b-list-group-item v-if="complexSelected.indexOf(1) !== -1">
        first
        <span class="break"></span>
        <b-button v-b-modal="'comp1'">Show Houses</b-button>
      </b-list-group-item>

      <b-list-group-item v-if="complexSelected.indexOf(2) !== -1">
        second
        <span class="break"></span>
        <b-button v-b-modal="'comp2'">Show Houses</b-button>
      </b-list-group-item>

      <b-list-group-item v-if="complexSelected.indexOf(3) !== -1">
        third
        <span class="break"></span>
        <b-button v-b-modal="'comp3'">Show Houses</b-button>
      </b-list-group-item>

      <b-list-group-item v-if="complexSelected.indexOf(4) !== -1">
        fourth
        <span class="break"></span>
        <b-button v-b-modal="'comp4'">Show Houses</b-button>
      </b-list-group-item>
    </b-list-group>


    <ul id="housesList1" v-if="houses_1_selected.length > 0">
      <li v-for="(id) in houses_1_selected" v-bind:key="id">
        {{ findHouse(id, houses_1) }}
      </li>
    </ul>

    <ul id="housesList2" v-if="houses_2_selected.length > 0">
      <li v-for="(id) in houses_2_selected" v-bind:key="id">
        {{ findHouse(id, houses_2) }}
      </li>
    </ul>

    <ul id="housesList3" v-if="houses_3_selected.length > 0">
      <li v-for="(id) in houses_3_selected" v-bind:key="id">
        {{ findHouse(id, houses_3) }}
      </li>
    </ul>

    <ul id="housesList4" v-if="houses_4_selected.length > 0">
      <li v-for="(id) in houses_4_selected" v-bind:key="id">
        {{ findHouse(id, houses_4) }}
      </li>
    </ul>

    <!-- The modal -->
    <b-modal id="comp">
      <div>
        <b-form-select class="choose" v-model="complexSelected" :options="apComplex" multiple :select-size="10"></b-form-select>
      </div>
    </b-modal>

    <b-modal id="comp1">
      <div>
        <b-form-select class="choose" v-model="houses_1_selected" :options="houses_1" multiple :select-size="10"></b-form-select>
      </div>
    </b-modal>

    <b-modal id="comp2">
      <div>
        <b-form-select class="choose" v-model="houses_2_selected" :options="houses_2" multiple :select-size="10"></b-form-select>
      </div>
    </b-modal>

    <b-modal id="comp3">
      <div>
        <b-form-select class="choose" v-model="houses_3_selected" :options="houses_3" multiple :select-size="10"></b-form-select>
      </div>
    </b-modal>

    <b-modal id="comp4">
      <div>
        <b-form-select class="choose" v-model="houses_4_selected" :options="houses_4" multiple :select-size="10"></b-form-select>
      </div>
    </b-modal>
  </div>
</template>

<script>

import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'


export default {
  name: 'App',
  components: {
  },
  data() {
      return {
        msg: 'hi',
        complexSelected: [],
        houses_1_selected: [],
        houses_2_selected: [],
        houses_3_selected: [],
        houses_4_selected: [],
        apComplex: [
          { value: 0, text: 'first' },
          { value: 1, text: 'second' },
          { value: 2, text: 'third' },
          { value: 3, text: 'fourth' },
        ],
        houses_1: [
          { value: 4, text: 'lenina, 86' },
          { value: 5, text: 'lenina, 89' }
        ],
        houses_2: [
          { value: 6, text: 'popova, 128' },
          { value: 7, text: 'popova, 131' }
        ],
        houses_3: [
          { value: 8, text: 'komsomplskaya, 53' },
          { value: 9, text: 'komsomplskaya, 58' },
          { value: 10, text: 'komsomplskaya, 62' }
        ],
        houses_4: [
          { value: 8, text: 'vorovskogo, 11' },
          { value: 9, text: 'vorovskogo, 12' }
        ]
    }
  },
  methods: {
    findHouse(id, mas) {
      for (let i=0; i < mas.length-1; i++) {
        console.log('------', mas[0].text, id)
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.choose {
  min-width: 400px;
}

.break {
  min-width: 100px;
}
</style>
