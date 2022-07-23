<script>
import LoadingPage from './LoadingPage.vue';


export default {
  data() {
    return {
      image: '',
      alt: '',
      loaded: false
    }
  },
  created() {
    this.firstFumo();
  },
  methods: {
    async firstFumo() {
      const req = await fetch('https://fumo-api.nosesisaid.me/random');
      const data = await req.json()
      this.image = data.URL;
      this.alt = data._id;
      this.loaded = true;
    },

    async anotherFumo() {
      const req = await fetch('https://fumo-api.nosesisaid.me/random');
      const data = await req.json()
      this.image = data.URL;
      this.alt = data._id;
      this.loaded = false
      setTimeout(() => {
        this.loaded = true
      }, 1000);

    }
  },
  components: { LoadingPage }
}
</script>

<template>
  <div v-if="loaded">
    <section class="flex h-screen text-white items-center justify-center">

      <!-- The Fumo Image-->
      <img :src="image" :alt="alt" class="object-cover rounded-lg h-auto w-[600px]" />

      <button v-if="loaded" @click="anotherFumo" type="button"
        class="px-4 py-2 m-5  font-sans font-semibold text-sm bg-green-400 text-white rounded-lg shadow-sm">
        Reload </button>
      <LoadingPage v-else />

    </section>
  </div>
  <LoadingPage v-else />

</template>