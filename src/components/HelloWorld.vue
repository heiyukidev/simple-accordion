<template>
  <div>
    <div>
      <h2>First example</h2>
      <Accordion :levels="[level1,level2,level3]"></Accordion>
      <Accordion :levels="[level1,level3]"></Accordion>
      <Accordion :levels="[level2,level1]"></Accordion>
    </div>
    <h2>Second example</h2>
    <div style="margin-top:20px">
      <Accordion2 :levels="[level1,level2,level3]"></Accordion2>
    </div>
  </div>
</template>

<script>
const Accordion = () => import("./Accordion");
const Accordion2 = () => import("./Accordion2");
export default {
  name: "HelloWorld",
  data() {
    return {
      level1: [
        {
          title: "level 1 T1",
          href: "level 1 T1"
        },
        {
          title: "level 1 T2",
          href: "level 1 T2"
        },
        {
          title: "level 1 T3",
          href: "level 1 T3"
        }
      ],
      level2: [
        {
          title: "level 2 T1",
          href: "level 2 T1"
        },
        {
          title: "level 2 T2",
          href: "level 2 T2"
        },
        {
          title: "level 2 T3",
          href: "level 2 T3"
        }
      ],
      level3: [
        {
          title: "level 3 T1",
          href: "level 3 T1"
        },
        {
          title: "level 3 T2",
          href: "level 3 T2"
        },
        {
          title: "level 3 T3",
          href: "level 3 T3"
        }
      ]
    };
  },
  components: {
    Accordion,
    Accordion2
  }
};
</script>

<style scoped>

</style>
