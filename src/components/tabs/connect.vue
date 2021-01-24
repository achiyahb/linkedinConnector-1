<template>
  <div style="display: grid; grid-template-rows: 25% 25% 25% 25%; height: 100%; background-color: #12232E; ">

    <div class="partOne" >
      <p class="oneP q-pa-none q-mr-none" >How many people you wish to connect?</p>
      <q-input   v-model="howMany" @focusout="pplNumber()" class="oneIn"  label="  We Recommend 80 max" bg-color="blue-grey-4"  >
        <template v-slot:append>
          <q-icon name="account_circle" color="blue-grey-9"  />
        </template>
      </q-input>

    </div>

    <div class="partTwo">
      <p class="pTwo" >option: choose word to avoid or  detect</p>
        <q-input class="twoIn"  label="Enter Keyword" bg-color="blue-grey-4">

        </q-input>
        <q-select  class="twoSelect" filled v-model="specification" :options="options" label="Select"  bg-color="blue-grey-4" />
    </div>

    <div class="partThird">
    <p class="pThird" >Are you interested in running the bot in trial or real mode?</p>
      <q-select  class="thirdSelect" filled v-model="modeStatus" :options="mode" label="Select" bg-color="blue-grey-4"  />
    </div>

    <div class="partFour">
      <q-checkbox v-model="right" label="I Confirm that i'm aware that the use of this bot is in my own responsibility"  />
        <q-btn  label="Connect members now" />
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
      ],
      howMany: null,
    }
  },
  methods: {
    pplNumber(){
      let self = this
      this.$q.bex.send('howMany',{number: this.howMany}).then(res => {
        console.log(res)
        self.howMany = null
        debugger
        console.log('background is back')
      }).catch(err => {
        alert(err)
      })
    },
  },

}
</script>

<style scoped>


* {
  margin: 0;
  padding: 0;
}


.partOne{
  display: grid;
  grid-template-columns: 50% 50%;
  background-color: #203647;
  padding: 0 5px
}


.oneP{
  justify-self: center;
  align-self: center;
}

.partTwo{
  display: grid;
  grid-template-columns: 35% 40% 25%;
  background-color: #213647;
  padding: 0 5px

}


.pTwo{
  justify-self: center;
  align-self: center;}




.partThird{
  display: grid;
  grid-template-columns: 50% 50%;
  background-color: #203647;
  padding: 0 5px

}
.partFour{
  background-color: #203647;
  padding: 0 5px 5px 5px;
  display: grid;
  grid-auto-rows: auto auto;
}


.pThird{
  justify-self: center;
  align-self: center;
}


.twoIn{
  padding-right: 5px;
  justify-self: center;
  align-self: center;


}
</style>
