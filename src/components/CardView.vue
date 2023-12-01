<template>
  <div>
    <div class="card">
      <span class="card-title">
        {{ data.title }}
      </span>
      <p class="card-details">
        {{ data.description }}
      </p>
      <button class="button" @click="onClick()">click</button>
      <div
        style="
          position: relative;
          width: 100%;
          height: 100%;
          display: flex;
          justify-content: center;
          margin-bottom: 100px;
          margin-top: 30px;
        "
        v-if="firstOne"
      >
        <div
          v-for="d in data.children"
          :key="d.id"
          style="width: 100%; height: 100%"
        >
          <BoxView
            :data="d"
            style="z-index: 10"
            @child-action="handleChildAction(e)"
          />
          <div v-if="secondOne" style="position: absolute; top: 20%; left: 5%">
            <div
              v-for="d1 in d.children"
              :key="d1.id"
              style="background: green"
            >
              <BoxView :data="d1" @child-action="handleChildAction" />

              <div style="position: absolute; top: 30%; left: 8%">
                <div v-for="d2 in d1.children" :key="d2.id">
                  <BoxView :data="d2" @child-action="handleChildAction" />
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BoxView from "@/components/box/BoxView";
export default {
  props: {
    data: Array,
  },
  data() {
    return {
      firstOne: false,
      secondOne: false,
      thirdOne: false,
    };
  },
  computed: {
    showData() {
      return this.data.children[0].children;
    },
  },
  components: {
    BoxView,
  },
  methods: {
    onClick() {
      this.firstOne = !this.firstOne;
    },

    handleChildAction(e) {
      this.secondOne = !this.secondOne;
    },
  },
};
</script>

