<template>
  <div>
    <div>

      <ul v-for="(cai,i) in caipu">
        <li>{{cai.name}}</li>
      </ul>

    </div>
  </div>
</template>
<script>
  export default {
    props: ['caipu'],
    mounted() {
      console.log(this.props)
    },
  }
</script>