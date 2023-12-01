<template>
  <div class="flex w-full h-auto px-5 py-0 bg-red-600 card-view">
    <CardView v-for="detail in details" :key="detail.id" :data="detail" />
  </div>
</template>

<script>
import detailInfo from "../details";
import CardView from "@/components/CardView";

export default {
  data() {
    return {
      details: detailInfo,
    };
  },

  components: {
    CardView,
  },
};
</script>

<style scoped>
.card-view{
    display: flex;
    justify-content: center;
    height:100% ;
    width: 100%;
    grid-gap: 20px;
    /* padding: 20px; */
    overflow: hidden;
}
</style>

