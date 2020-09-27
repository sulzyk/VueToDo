<template>
    <div class="MyPositionWrapper">
        <label for="btnEdit">{{recordName}}</label>
        <button class="btnEdit" > Edytuj </button>
        <button class="btnDelete" @click="DelPos"> Usuń </button>
    </div>
</template>

<script>
export default {
    name: "MyPosition",
    props: {
        recordName: {
            type: String,
            default: '',
        },
        recordIndex: {
            type: Number,
            required: true,
        },
        myArray: {
            type: Array,
            required: true,
        },
    },
    methods: {
        DelPos(){
            this.myArray.splice(this.recordIndex,1);
        },
        EditPos() {
            this.$emit('edit', true);
        },
    },
}
</script>

<style scoped>
    .MyPositionWrapper{
        display: flex;
        flex-direction: row;
        margin-top: 25px;
        margin-bottom: 25px;
    }
    .btnEdit{
        margin-left: 15px;
    }
    .btnDelete{
        margin-left: 15px;
    }

</style>