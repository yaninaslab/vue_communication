<template>
    <div>
<button @click="click_button" ref="btn">Button 1</button>
    </div>
</template>

<script>
import cookies from 'vue-cookies';
    export default {
        name: "button-one",
        methods: {
            click_button() {
                this.$emit('button_clicked', "Button One Clicked!");
                this.$refs['btn'].style.background = "pink";
                cookies.remove("kanye_quote");
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