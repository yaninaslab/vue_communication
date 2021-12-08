<template>
    <div>
<button @click="press_button_two" ref="btn">Button 3</button>
    </div>
</template>

<script>
    export default {
        name: "button-three",
        methods: {
            press_button_two() {
                this.$emit('button_clicked', "Button Three Clicked!");
                this.$refs['btn'].style.background = "red";
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