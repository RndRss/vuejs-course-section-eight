<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{ switchName() }}</p>
        <button @click="resetName">Reset Nane</button>
    </div>
</template>

<script>
    export default {
        props: {
            myName: {
                type: String,
                default: 'Name2'
            }
        },
        methods: {
            switchName() {
                return this.myName.split("").reverse().join("");
            },
            resetName() {
                this.myName = "NAMEEE";
                this.$emit('nameWasReset', this.myName);

            }
        }
    }
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
