<template>
  <div>
    Copyright© {{ year }} Gentry Way Co., Ltd.
  </div>
</template>

<script>
export default {
  name: 'CopyrightText',
  data() {
    return {
      year: new Date().getFullYear(),
    }
  },
}
</script>

<style scoped>
div {
  box-sizing: border-box;
  max-width: max-content;
  margin-left: auto;
  font-size: 75%;
}

@media only screen and (min-width: 481px) {
  div {
    margin-right: 0;
  }
}

@media only screen and (max-width: 480px) {
  div {
    margin-right: auto;
  }
}
</style>
