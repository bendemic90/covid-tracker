<template>
  <Header />
  <div class="container-flex p-5">
    <router-view/>
  </div>
</template>

<script>
  import Header from '@/components/Header'

  export default {
    components: {
      Header
    },
  };
</script>