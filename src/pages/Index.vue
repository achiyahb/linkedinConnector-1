<template>
  <div class="flex flex-center">
<mainPage/>
  </div>
</template>

<script>
import mainPage from"../components/mainPage"

export default {
  name: 'PageIndex',
  components: {mainPage},
}
</script>

<style scoped >
.flex flex-center{
  width: 500px;
  height: 500px;

}
</style>
