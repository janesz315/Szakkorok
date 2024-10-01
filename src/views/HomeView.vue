<template>
  <h1 class="text-center my-4">Szakkörök kezelése</h1>

  <div class="container my-border">
    <div class="row">
      <!-- Tanulók Táblázata -->
      <div class="col-12 col-md-6 mb-4">
        <div class="table-responsive">
          <table class="table table-bordered border-success table-hover table-striped table-success shadow-sm">
            <thead >
              <tr>
                <th>Név</th>
                <th>Osztály</th>
                <th>Szakkör</th>
              </tr>
            </thead>
            <tbody>
              <!-- A tanulók neve és osztályuk -->
              <tr v-for="(tanulo, i) in tanulok" :key="i">
                <td>{{ tanulo.nev }}</td>
                <td>{{ tanulo.osztaly }}</td>
                <!-- szakkörök kiválasztása -->
                <td>
                  <select
                    class="form-select form-select-sm"
                    aria-label="Small select example"
                    v-model="tanulo.szakkorId"
                  >
                    <option disabled value="">Válassz szakkört</option>
                    <option v-for="(szakkor, ind) in szakkorok" :key="ind" :value="szakkor.id">
                      {{ szakkor.nev }}
                    </option>
                  </select>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <!-- Szakkör Kártyák -->
      <div class="col-12 col-md-6 d-flex flex-column">
        <SzakkorKartya :szakkorok="szakkorok" :tanulok="tanulok" />
      </div>
    </div>
  </div>
</template>

<script>
import SzakkorKartya from '@/components/SzakkorKartya.vue';

export default {
  components: {
    SzakkorKartya,
  },
  data() {
    return {
      tanulok: [
        { id: 1, nev: 'AVE', osztaly: '13d', szakkorId: 1 },
        { id: 2, nev: 'Lexus_DC', osztaly: '13d', szakkorId: 1 },
        { id: 3, nev: 'Farlix', osztaly: '13d', szakkorId: 1 },
        { id: 4, nev: 'Amy', osztaly: '13d', szakkorId: 1 },
        { id: 5, nev: 'ItzKat1', osztaly: '13d', szakkorId: 1 },
        { id: 6, nev: 'surix', osztaly: '13d', szakkorId: 1 },
        { id: 7, nev: 'Begi', osztaly: '13d', szakkorId: 1 },
        { id: 8, nev: 'SanielShadowX', osztaly: '13a', szakkorId: 1 },
        { id: 9, nev: 'Aaron Collins', osztaly: '13d', szakkorId: 1 },
        { id: 10, nev: 'Patr1ck01', osztaly: '14d', szakkorId: 1 },
        { id: 11, nev: 'Romain', osztaly: '13d', szakkorId: 1 },
        { id: 12, nev: 'crypted', osztaly: '13e', szakkorId: 1 },
        { id: 13, nev: 'skulleewag', osztaly: '13e', szakkorId: 1 },
        { id: 14, nev: 'Kacper Jarzynski', osztaly: '13e', szakkorId: 3 },
        { id: 15, nev: 'huh_bokii', osztaly: '13a', szakkorId: 1 },
        { id: 16, nev: 'DimaNastart', osztaly: '13b', szakkorId: 1 },
        { id: 17, nev: 'JackusEditz', osztaly: '13c', szakkorId: 1 },
        { id: 18, nev: 'shizaseen', osztaly: '13d', szakkorId: 1 },
      ],
      szakkorok: [
        { id: 1, nev: 'Nem jár szakkörre' },
        { id: 2, nev: 'Történelem' },
        { id: 3, nev: 'Matematika' },
        { id: 4, nev: 'Gamer' },
      ],
    };
  },
};
</script>

<style>
.my-border {
  border: 4px groove blue;
  padding: 20px;
  background-color: #f9f9f9;
}

.table {
  border-radius: 10px;
  overflow: hidden;
}

.table-responsive {
  width: 100%;
  overflow-x: auto;
}

.card {
  background-color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  padding: 10px;
  
}

.card-body {
  padding: 20px;
}

h1 {
  color: #343a40;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1.5px;
}

@media (max-width: 768px) {
  .my-border {
    padding: 10px;
  }

  .table {
    font-size: 0.9rem;
  }

  .card {
    padding: 15px;
  }

  h1 {
    font-size: 1.5rem;
  }
}
</style>
