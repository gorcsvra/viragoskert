<template>
  <div class="container-fluid bg-image">

     
      <link
        href="https://fonts.googleapis.com/css2?family=Fira+Code&display=swap"
        rel="stylesheet"
      />
      <link
        href="https://fonts.googleapis.com/css2?family=Acme&display=swap"
        rel="stylesheet"
      />

      <form method="post" @submit.prevent="szamol">
        <div class="wrapper">
          <div class="box box1">
            <div class="description">
              <h2>Adatok</h2>
              <label for="kertSzelesség"> <p><strong>Kertszélesség: </strong></p></label>
              <input type="number" id="kertSzelesseg" v-model="kertSzelesseg" />
              <label for="kertHosszusag"><p><strong> Kerthosszúság:</strong></p> </label>
              <input type="number" id="kertHosszusag" v-model="kertHosszusag" /><span>m</span>
              <button type="submit" class="glass2"><p><strong>Számol</strong></p> </button>
            </div>
          </div>

          <div class="box box2">
            <div class="description">
              <h2>Eredmény</h2>
              <p><strong>Tulipánok száma: </strong>{{ tulip }}<span>db</span></p>
              <p><strong>Rózsák száma: </strong>{{ rozsa }}<span>db</span></p>
            </div>
          </div>
        </div>
      </form>
  
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      kertSzelesseg: "",
      kertHosszusag: "",
      tulip: "",
      rozsa: "",
    };
  },
  methods: {
    szamol() {
      this.tulip =
        (Math.floor(this.kertSzelesseg / 2 / 0.4) + 1) *
        (Math.floor(this.kertHosszusag / 0.4) + 1);
      this.rozsa =
        (Math.floor(this.kertSzelesseg / 2 / 0.6) + 1) *
        (Math.floor(this.kertHosszusag / 0.6) + 1);
    },
  },
};
</script>
