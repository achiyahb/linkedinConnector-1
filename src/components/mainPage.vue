<template>
  <div>


  <q-card id="tabs" >

    <q-tabs
      v-model="tab"
      indicator-color="transparent"
      active-color="white"
      class="bg-teal text-grey-5 shadow-2"
    >

      <q-tab name="search" icon="mail" label="By Search" />
      <q-tab name="withdraw" icon="alarm" label="Withdraw" />
      <q-tab name="connect" icon="movie" label="Connect" />

    </q-tabs>
    <q-tab-panels  v-model="tab" animated >
      <q-tab-panel name="search">
        <bySearch/>
      </q-tab-panel>

      <q-tab-panel name="withdraw">
        <withdraw/>
      </q-tab-panel>

      <q-tab-panel name="connect">
        <connect/>
      </q-tab-panel>
    </q-tab-panels>


  </q-card>
  </div>
</template>

<script>

import bySearch from "components/tabs/bySearch";
import connect from "components/tabs/connect";
import withdraw from "components/tabs/withdraw";
export default {
name: "mainPage",
  components:{
  bySearch,
    connect,
    withdraw
  },
  data() {
    return {
      tab: 'active',
    }
  },
}
</script>

<style scoped>
#tabs{
  width: 500px;
}
</style>
