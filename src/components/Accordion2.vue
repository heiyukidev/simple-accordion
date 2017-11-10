<template>
  <div>
    <div v-for="(level,i) in current" :key="level._id">
      <a :href="level.href">{{level.title}}</a><br>
      <div style="margin-left:20px" v-if="getChildren(i).length>0">
        <Accordion2 :levels="getChildren(i)"></Accordion2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Accordion2",
  props: {
    levels: {
      type: Array,
      required: true
    }
  },
  computed: {
    current() {
      if (this.levels && this.levels[0]) {
        return this.levels[0];
      }
      return [];
    }
  },
  methods: {
    getChildren(i) {
      //this will return level 2 for the first element.
      // level 3 for the second
      // I didn't understand exactly how you convert levels but i hope these examples are good
      return this.levels.filter((l, idx) => {
        if (i + 1 === idx) {
          return true;
        }
        return false;
      });
    }
  }
};
</script>

<style>

</style>
