<template>
  <div>
    <div v-for="szakkor in szakkorok" :key="szakkor.id" class="card" style="width: auto; margin-bottom: 20px;">
      <div class="card-body">
        <!-- név és tagszám -->
        <h5 class="card-title">{{ szakkor.nev }}: {{ filteredTanulok(szakkor.id).length }} tag</h5>
        <p class="card-text">
          <!-- Ha 0 tag van -->
          <span v-if="filteredTanulok(szakkor.id).length === 0">Nincs tanuló ebben a szakkörben</span>
          <!-- Ha van legalább 1 tag -->
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
    // Szűri azokat a tanulókat, akik az adott szakkörhöz tartoznak
    filteredTanulok(szakkorId) {
      return this.tanulok.filter((tanulo) => tanulo.szakkorId === szakkorId).sort((a, b) => a.nev.localeCompare(b.nev));
    },
  },
};
</script>

<style scoped>
.card {
  border: 2px solid green;
}
</style>
