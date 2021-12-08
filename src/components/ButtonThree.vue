<template>
  <div>
    <button @click="press_button_two" ref="btn">Button 3</button>
  </div>
</template>

<script>
import axios from 'axios';
import cookies from 'vue-cookies';
    export default {
        name: "button-three",
        methods: {
            press_button_two() {

                axios.request({
                    url: "https://api.kanye.rest"

                }).then((response) => {
                    var quote = response.data['quote'];
                    this.$emit('button_clicked', quote);
                    cookies.set("kanye_quote", quote);
                }).catch((error) => {
                    error;
                    this.$emit('button_clicked', "Issue with API, sorry");

                });

        
               //this.$refs['btn'].style.background = "red";
            },
            party_time() {
                this.$refs['btn'].innerText = "Let's Party!";
                this.$refs['btn'].style.background = "lightgreen";

            }
        },
        mounted () {
            this.$root.$on('party_time', this.party_time);
        },
    
    }
</script>

<style scoped>
</style>