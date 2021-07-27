<template>
  <main v-if="!loading">
    Covid Tracker
  </main>
  <main v-else class="flex flex-col align-center justify-center text-center">
    <div class="text-gray-500 text-3xl mt-10 mb-6">
    Fetching Data
    </div>
    <img :src="loadingImage" alt="timer" class="w-24 m-auto" />
  </main>
</template>

<script>
export default {
  name: 'Home',
  components: {},
  data() {
    return {
    loading: true,
    title: 'Global',
    dataDate: '',
    stats: {},
    countries: [],
    loadingImage: require('../assets/hourglass.gif')
    }
  },
  methods: {
    async fetchData() {
      const res = await fetch("https://api.covid19api.com/summary");
      const data = await res.json();
      return data
    },
  },
  async created() {
    const data = await this.fetchData();
    this.dataDate = data.Date;
    this.stats = data.Global;
    this.countries = data.Countries;
    this.loading = false;
  },
}
</script>