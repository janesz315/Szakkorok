<template>
  <h1 class="text-center">Szakkörök</h1>
    
  <div class="container container-fluid my-border">
     
  <div class="row">
    <div class="col col-6">
      <table class="table table-bordered border-success table-hover table-striped table-success">
        <thead>
          <tr>
            <th>Név</th>
            <th>Osztály</th>
            <th>Szakkör</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(tanulo, i) in tanulok" :key="i">
            <td>{{ tanulo.nev }}</td>
            <td>{{ tanulo.osztaly }}</td>
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

    <div class="col col-6 mt-2">
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
        { id: 2, nev: 'Lexus_DC', osztaly: '13d', szakkorId: 4 },
        { id: 3, nev: 'Farlix', osztaly: '13d', szakkorId: 2 },
        { id: 4, nev: 'Amy', osztaly: '13d', szakkorId: 3 },
        { id: 5, nev: 'ItzKat1', osztaly: '13d', szakkorId: null },
        { id: 6, nev: 'surix', osztaly: '13d', szakkorId: null },
        { id: 7, nev: 'Begi', osztaly: '13d', szakkorId: 1 },
        { id: 8, nev: 'SanielShadowX', osztaly: '13a', szakkorId: null },
        { id: 9, nev: 'Aaron Collins', osztaly: '13d', szakkorId: null },
        { id: 10, nev: 'Patr1ck01', osztaly: '14d', szakkorId: null },
        { id: 11, nev: 'Romain', osztaly: '13d', szakkorId: 2 },
        { id: 12, nev: 'crypted', osztaly: '13e', szakkorId: null },
        { id: 13, nev: 'skulleewag', osztaly: '13e', szakkorId: null },
        { id: 14, nev: 'Kacper Jarzynski', osztaly: '13e', szakkorId: 3 },
        { id: 15, nev: 'huh_bokii', osztaly: '13a', szakkorId: 4 },
        { id: 16, nev: 'DimaNastart', osztaly: '13b', szakkorId: null },
        { id: 17, nev: 'JackusEditz', osztaly: '13c', szakkorId: null },
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


.card {
  background-color: #fff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
  padding: 10px;
  margin-bottom: 15px;
}

.card-body {
  padding: 20px;
  text-decoration: none;
}

h1 {
  color: #343a40;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1.5px;
}

</style>

