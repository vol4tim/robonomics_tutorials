<template>
  <div>
    <b>Liability smart contract: </b>{{ liability.address }}<br/>
    <b>lighthouse: </b>{{ liability.lighthouse }}<br/>
    <b>provider: </b>{{ liability.worker }}<br/>
    <b>model: </b>{{ liability.model }}<br/>
    <b>objective: </b>{{ liability.objective }}<br/>
    <b>token: </b>{{ liability.token }}<br/>
    <b>price: </b>{{ liability.cost }}<br/>
    <b>user address: </b>{{ liability.promisee }}<br/>
    <b>Aira: </b>{{ liability.promisor }}<br/>
    <span v-if="liability.result != ''">
      <b>Results: </b>{{ liability.result }}
      <v-icon v-if="liability.check === true" large color="green darken-2">mdi-check</v-icon>
      <v-icon v-if="liability.check === false" large color="blue-grey darken-2">mdi-alert-circle-outline</v-icon>
      <br/>
      <span v-for="(res, resIndex) in liability.resultMessage" :key="resIndex">
        {{ res }}<br />
      </span>
    </span>
    <span v-if="liability.result == ''">
      <b>Results: </b><v-progress-linear :indeterminate="true"></v-progress-linear>
    </span>
  </div>
</template>

<script>
export default {
  name: 'Liability',
  props: ['liability']
}
</script>

<style lang="css">
.fill-row {
  flex: 0 0 100%;
  margin-top: 20px;
  margin-bottom: 20px;
}
#div-with-loading {
  width: 200px;
  height: 200px;
  margin: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid #444;
  border-radius: 5px;
}
</style>
