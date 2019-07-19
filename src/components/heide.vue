<template>
  <div>
    <h2>99999999</h2>
    <h2>{{a}}</h2>
  </div>
</template>
<script>
  export default {
    props: ["a"],
    methods: {

    },
    mounted() {
      console.log(this.a)
    },
  }
</script>