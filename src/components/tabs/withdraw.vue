<template>
  <div>
    <div>
      <p>Check connection request times</p>
      <q-btn label="Check" />
    </div>

<div>
  <p>Choose requests times to Withdraw</p>
  <q-btn label="??????" />
</div>

    <div>
      <p>Withdraw from the invitation requests</p>
      <q-select filled  label="????" />
    </div>


    <div>
      <p>Are you interested in running the bot in trial or real mode?</p>
      <q-select filled v-model="modeStatus" :options="mode" label="Select" />
    </div>

    <div>
      <q-checkbox v-model="right" label="I Confirm that i'm aware that the use of this bot is in my own responsibility" />
      <q-btn label="Connect members now" />
    </div>
  </div>
</template>

<script>
export default {
  name: "withdraw",
  data(){
    return{
      right: false,
      mode: [
        'Trial', 'Real mode'
      ],
      modeStatus: null,

    }
  }
}
</script>

<style scoped>

</style>
