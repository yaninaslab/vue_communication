<template>
    <div>
<button @click="party_time_now">PARTY TIME!</button>
    </div>
</template>

<script>
    export default {
        name: "party-button",
        methods: {
            party_time_now() {
                this.$root.$emit('party_time');
            }
        },
        mounted () {
            this.$root.$on('party_time', this.party_time);
        },
    }
</script>

<style scoped>

</style>