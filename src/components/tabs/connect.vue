<template>
  <div>

    <div class="partOne">
      <p>How many people you wish to connect?</p>
      <q-input label="We recommend no more than 80"  />
    </div>

    <div class="partTwo">
      <p>option: choose word to avoid or  detect</p>
      <div>
        <q-input/>
        <q-select filled v-model="specification" :options="options" label="Select" />
      </div>
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
  name: "connect",
  data () {
    return {
      specification: null,
      modeStatus: null,
      right: false,
      options: [
        'Detect', 'Avoid'
      ],
      mode: [
        'Trial', 'Real mode'
      ]
    }
  }

}
</script>

<style scoped>

</style>
