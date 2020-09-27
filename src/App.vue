<template>
  <div class="wrapper">
    <Header />
    <InputForNewRecord v-model="testValue"/>
    
    <MyPosition 
      v-for="(item, index) in testValue" :key="item" 
      :recordName=item
      :recordIndex=index
      :myArray=testValue
      v-model="testValue"
    />
    <EditModal v-if="modalOpen" />
  </div>  
</template>

<script>
import Header from "./components/Header.vue"
import InputForNewRecord from "./components/InputForNewRecord.vue"
import MyPosition from "@/components/MyPosition.vue"
import EditModal from "@/components/EditModal.vue"

export default {
  name: 'App',
  components: {
    Header,
    InputForNewRecord,
    MyPosition,
    EditModal,
  },
  data(){
    return {
      testValue: [],
      modalOpen: false
    };
  },
}
</script>

<style>
  .wrapper {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
