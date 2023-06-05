<template>
<div class="column">
  <div class="column__title">
    {{ title }}
  </div>
  <Card 
    v-for="(item, index) in filteredOffers"
    :key="index"
    :contactName="item.CONTACT_TITLE"
    :id="item.OFFER_ID"
    :offerType="item.OFFERS_TYPE_NAME"
    :segment="item.SEGMENT_NAME"
  />
</div>
  
</template>

<script>
import Card from './Card.vue'
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    statusName: {
      type: String,
      required: true
    },
    offers: {
      type: Array,
      required: true
    }
      
  },

  components: {
    Card
  },

  computed: {
    filteredOffers() {
      return this.offers.filter( el => el.STATUS_NAME === this.statusName )
    }
  }
};
</script>

<style lang="scss" scoped>
.column {
width: calc(100% / 9) ;
display: flex;
flex-direction: column;
align-items: center;

  &__title {
    margin-bottom: 20px;
    font-size: 14px;
    text-align: center;
    
  }
}
</style>