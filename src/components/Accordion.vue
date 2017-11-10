<template>
    <div style="margin-left:50px;">
        <div v-for="level in current" :key="level._id">
            <a :href="level.href">{{level.title}}</a><br>
        </div>
        <div v-if="children.length>0">
            <Accordion :levels="children"></Accordion>
        </div>
    </div>
</template>

<script>
export default {
  name: "Accordion",
  props: {
    levels: {
      type: Array,
      required: true
    }
  },
  computed: {
    current() {
      //this will return level 1
      if (this.levels && this.levels[0]) {
        return this.levels[0];
      }
      return [];
    },
    children() {
      //this will return all the levels execpt level 1
      return this.levels.filter((l, i) => {
        if (i !== 0) {
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
