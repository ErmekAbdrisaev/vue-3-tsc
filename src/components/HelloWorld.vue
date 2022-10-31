<template>
  <div class="hello">
    <h1>ОТДЕЛЕНИЯ И БАНКОМАТЫ ОПТИМА БАНК</h1>
  </div>
  <ul>
    <li>
      <a
        href="https://www.optimabank.kg/images/files/news/2014/spisok-bankomatov-oao-optima-bank.pdf"
        >Список Банкоматов Оптима Банк СКАЧАТЬ (pdf)</a
      >
    </li>
    <li>
      <a href="https://www.optimabank.kg/images/files/pos_terminals.pdf"
        >Список POS-терминалов ОАО «Оптима Банк»</a
      >
    </li>
    <li>
      <a href="https://www.optimabank.kg/images/files/cashin_terminals_list.pdf"
        >Список платежных терминалов ОАО «Оптима Банк»</a
      >
    </li>
    <li>
      <a
        href="https://www.optimabank.kg/images/files/news/2015/09/spisok_podrazdeleniy_oao_optima_bank_s_telefonami_i_adresami.pdf"
        >Справочник подразделений в ОАО «Оптима Банк» (адрес и режим работы)"</a
      >
    </li>
  </ul>

  <GMapMap
    :center="center"
    :zoom="7"
    map-type-id="terrain"
    style="width: 500px; height: 300px"
  >
    <GMapCluster>
      <GMapMarker
        :key="index"
        v-for="(m, index) in markers"
        :position="m.position"
        :clickable="true"
        :draggable="true"
        @click="center = m.position"
      />
    </GMapCluster>
  </GMapMap>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "HelloWorld",
  data() {
    return {
      center: { lat: 51.093048, lng: 6.84212 },
      markers: [
        {
          position: {
            lat: 51.093048,
            lng: 6.84212,
          },
        }, // Along list of clusters
      ],
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  font-size: 1.76em;
  margin: 40px 0 0;
  color: #e2001a;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  font-size: 1.4em;
  display: block;
  margin: 10px 10px;
}
a {
  color: #e2001a;
}
</style>
