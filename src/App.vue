<script setup>
import ButtonsComp from "./components/ButtonsComp.vue"
import DATA from "../public/data.json"

function clickHandler() {
    let list = document.getElementById("list")
    let li = document.createElement("li")
  
    function filterByGroups(data) {
  
      const groups = data.reduce((currentData, person) => {
        currentData[person.group] = []
        return currentData
      }, {})
  
  
      Object.keys(groups).forEach(group => {
        const students = data.filter(person => person.group == group)
        groups[group] = students
      })
      return groups
    }
  
    const groups = filterByGroups(DATA)
    li.innerHTML = JSON.stringify(groups.Orchid)
    list.appendChild(li)
  
    return;
  }

</script>

<template>
  <div class="container">
    <ButtonsComp groupName="Orchid" @action="clickHandler"></ButtonsComp>
    <ButtonsComp groupName="SteelBlue"></ButtonsComp>
    <ButtonsComp groupName="IndianRed"></ButtonsComp>
    <ButtonsComp groupName="LightSeaGreen"></ButtonsComp>
    <ButtonsComp groupName="YellowGreen"></ButtonsComp>
  </div>

  <div class="students">
    <ul id="list">

    </ul>
  </div>
</template>


<style scoped>
.students {
  position: fixed;
  width: auto;
  height: auto;
  top: 350px;
  left: 150px;
}

</style>