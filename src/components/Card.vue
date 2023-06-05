<template>
  <div class="card">
    <div class="card__row">
      {{contactName}}
      </div>
      <div class="card__row">
        id сделки: {{id}}
      </div>
      <div class="card__row">
        {{segment}}
      </div>
  </div>
</template>

<script>
export default {
  props: {
    contactName: {
      type: String,
      required: true
    },
    id: {
      type: Number,
      required: true
    },
    // offerType: {
    //   type: String,
    //   required: true
    // },
    segment: {
      type: String,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped>
.card {
  padding: 10px;
  margin-bottom: 15px;
  font-size: 10px;
  box-shadow: 10px 10px 10px rgba($color: #000000, $alpha: 0.1);
  background: #fff;
  width: 90px;

  &__row {
    margin-bottom: 10px;
  }
}
</style>