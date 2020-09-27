<template>
    <div class="InputForNewRecordWrapper">
        <label for="NewToDo" class="lbInfo">Wpisz nazwę nowego zadania</label>
        <input
            type="text"
            id="NewToDo"
            name="NewToDo"
            class="NewToDo"
            placeholder="Wpisz nazwę"
            v-model="txtFromInput"
        />
        <button class="btnAdd" v-on:click="AddNewRecord"> Dodaj zadanie </button>
    </div>
</template>

<script>
export default {
    name: "InputForNewRecord",
    props: {
        value: {
            type: Array,
            required: true,
        },
    },
    data() {
        return {
            txtFromInput: '',
            myTab: [],
        };
    },
    methods: {
        AddNewRecord: function(e) {
            this.value.push(this.txtFromInput);
            this.$emit('click', e.target.value);
        },
    },
}
</script>

<style scoped>
    .InputForNewRecordWrapper {
        border: 10px;
        display: flex;
        flex-direction: column;
    }
    .lbInfo{
        font-size: 25px;
    }
    .NewToDo{
        font-size: 25px;
        border: 0px;
        border-bottom: 1px solid black;
    }   
    .btnAdd{
        margin-top: 25px;
    }
</style>