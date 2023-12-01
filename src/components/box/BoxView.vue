<template>
  <div class="box">
    <span class="box-title">
      {{ data.title }}
    </span>
    <p class="box-details">
      {{ data.description }}
    </p>
    <button class="button" @click="clickView" >
        click
      </button>
  </div>
</template>

<script>
import CardView from "../../components/CardView.vue";

export default {
  props: ["data"],

  data() {
    return {
      count:1,
    };
  },
  components: {
    CardView,
  },

  computed: {
    countData() {
      return this.allData.push(this.card);
    },
  },
  methods:{
    clickView(){
      this.count++;
      this.$emit('child-action');
    }
  },

  mounted() {
    // console.log(this.card.children)
  },
};
</script>

