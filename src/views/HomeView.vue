<template>
  <h1 class="text-center">Szakkörök</h1>

  <div class="container container-fluid my-border">
    <h1>Am I too cute to handle?</h1>
    <div class="col col-6">
      <table class="table table-bordered border-primary">
        <thead>
          <tr>
            
            <th >Név</th>
            <th >Osztály</th>
            <th >Szakkör</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            
            <td>Mark</td>
            <td>Otto</td>
            <td>@mdo</td>
          </tr>
          
        </tbody>
      </table>
    </div>

    <div class="col col-6"></div>
  </div>
</template>
<script>
export default {
  data(){
    return{
      tanulok:[
        {
          id:1,
          nev:"AVE",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:2,
          nev:"Lexus_DC",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:3,
          nev:"Farlix",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:4,
          nev:"Amy",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:5,
          nev:"ItzKat1",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:6,
          nev:"surix",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:7,
          nev:"Begi",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:8,
          nev:"SanielShadowX",
          osztaly: "13a",
          szakkorId: null
        },
        {
          id:9,
          nev:"Aaron Collins",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:10,
          nev:"Patr1ck01",
          osztaly: "14d",
          szakkorId: null
        },
        {
          id:11,
          nev:"Romain",
          osztaly: "13d",
          szakkorId: null
        },
        {
          id:12,
          nev:"crypted",
          osztaly: "13e",
          szakkorId: null
        },
        {
          id:13,
          nev:"skulleewag",
          osztaly: "13e",
          szakkorId: null
        },
        {
          id:14,
          nev:"Kacper Jarzynski",
          osztaly: "13e",
          szakkorId: null
        },
        {
          id:15,
          nev:"huh_bokii",
          osztaly: "13a",
          szakkorId: null
        },
        {
          id:16,
          nev:"DimaNastart",
          osztaly: "13b",
          szakkorId: null
        },
        
      ]
    }
  }

}

</script>



<style>
.my-border {
  border: 4px groove blue;
}
</style>