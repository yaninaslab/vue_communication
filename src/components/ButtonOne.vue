<template>
    <div>
<button @click="click_button" ref="btn">Button 1</button>
    </div>
</template>

<script>
    export default {
        name: "button-one",
        methods: {
            click_button() {
                this.$emit('button_clicked', "Button One Clicked!");
                this.$refs['btn'].style.background = "pink";
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