<template>
  <div>
    <h1 ref="btn_message_tag">{{ button_message }}</h1>
    <button-one @button_clicked="react_to_btn_clicked"> </button-one>

    <button-two @button_clicked="react_to_btn_clicked"></button-two>
    <button-three @button_clicked="react_to_btn_clicked"></button-three>
    <party-button></party-button>
  </div>
</template>

<script>
import ButtonOne from "./ButtonOne.vue";
import ButtonTwo from "./ButtonTwo.vue";
import ButtonThree from "./ButtonThree.vue";
import PartyButton from './PartyButton.vue'

export default {
  name: "home-content",

  methods: {
    react_to_btn_clicked(payload) {
      this.button_message = payload;
    },
    party_time() {
        this.$refs['btn_message_tag'].style.color = "purple";

    },
    mounted () {
        this.$root.$on('party_time', this.party_time);
    },
  },

  components: {
    ButtonOne,
    ButtonTwo,
    ButtonThree,
    PartyButton,
  },
  data() {
    return {
      button_message: undefined,
    };
  },
};
</script>

<style scoped>
</style>