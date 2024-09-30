<template>
  <div>
    <div v-for="szakkor in szakkorok" :key="szakkor.id" class="card" style="width: auto; margin-bottom: 20px;">
      <div class="card-body">
        <h5 class="card-title">{{ szakkor.nev }}</h5>
        <p class="card-text">
          <span v-if="filteredTanulok(szakkor.id).length === 0">Nincs tanuló ebben a szakkörben</span>
          <ul v-else>
            <li v-for="tanulo in filteredTanulok(szakkor.id)" :key="tanulo.id">{{ tanulo.nev }}</li>
          </ul>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    szakkorok: Array,
    tanulok: Array,
  },
  methods: {
    filteredTanulok(szakkorId) {
      return this.tanulok.filter((tanulo) => tanulo.szakkorId === szakkorId);
    },
  },
};
</script>

<style scoped>
.card {
  border: 2px solid green;
}
</style>
