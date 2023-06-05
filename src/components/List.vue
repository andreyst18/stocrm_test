<template>
  <div class="list">
    <Column 
      v-for="(item, index) in statuses"
      :key="index"
      :title="item.TITLE"
      :offers="offers"
      :statusName="item.TITLE"
      class="list__col"
    />
  </div>
</template>

<script>
import Column from "./Column.vue";
export default {
  props: {
    statuses: {
      type: Array,
      required: true
    },
    offers: {
      type: Array,
      required: true
    }
  },
  components: {
    Column,
  },
};
</script>

<style lang="scss" scoped>
.list {
  display: flex;
  justify-content: space-between;
  width: 100vw;
  
  
  &__col {
    padding-top: 20px;

    &:nth-child(2n) {
      background: #fff;
    }

    &:nth-child(2n+1) {
      background: #efeff0;
    }
    
  }
}

</style>