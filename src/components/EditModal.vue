<template>
    <div class="EditModalWrapper">
        <label for="EditField"> Nazwa zadania </label>
        <input class="EditField" {{myTab[recIndex]}}/>
        <button class="BtnSave"> Zapisz </button>       
    </div>    
</template>

<script>
export default {
    name: "EditModal",
    props:{
        recIndex: {
            type: String,
        }    ,
        recTxt: {
            type: String,
        },
        myTab: {
            type: Array,
        },
    },
    methods:{

    },
}
</script>

<style scoped>  
    .EditModalWrapper{
        display: flex;
        flex-direction: row;
        margin-top: 25px;
        margin-bottom: 25px;
        justify-content: center;
    }
    .EditField {
        margin-left: 15px;
    }
    .BtnSave{
        margin-left: 15px;
    }
</style>