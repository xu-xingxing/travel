<template>
    <div>
        <city-header></city-header>
        <city-search></city-search>
        <city-list :letter="letter" :hotCities="hotCities" :cities="cities"></city-list>
        <city-alphabet
          :cities="cities"
          @change="handleLetterChange"
        ></city-alphabet>
    </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  data () {
    return {
      hotCities: [],
      cities: {},
      letter: ''
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.handleCityInfoSucc)
    },
    handleCityInfoSucc (res) {
      res = res.data
      if (res.data && res.ret) {
        const data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style lang="stylus" scoped>

</style>
