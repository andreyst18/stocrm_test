<template>
  <div id="app">
    <List 
      :statuses="statuses" 
      :offers="offers" 
    />
  </div>
</template>

<script>
import List from "./components/List.vue";

export default {
  name: "App",

  data() {
    return {
      domen: "nastintesthodl",
      SID: "10813_0c0a9a2f86eab09196705a274378b64a",
      vNumber: "1843",
      statuses: [],
      offers: [],
    };
  },

  components: {
    List,
  },

  async mounted() {
    let response = await fetch(
      `https://${this.domen}.stocrm.ru/api/external/v1/offer/all_statuses?SID=${this.SID}&BOARD_ID=${this.vNumber}`
    );
    response = await response.json();
    console.log(response);
    this.statuses = Object.values(response.RESPONSE);
    this.statuses.sort((a, b) => a.SORT - b.SORT);
    console.log(this.statuses);

    let response1 = await fetch(
      `https://${this.domen}.stocrm.ru/api/external/v1/offers/get_from_filter?SID=${this.SID}`
    );
    response1 = await response1.json();
    console.log(response1);
    this.offers = Object.values(response1.RESPONSE.DATA);
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
</style>
