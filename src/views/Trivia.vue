<template>
  <div class="trivia">
    <h1>Elige la temática</h1>
<b-row>
  <b-col lg="4" class="pb-2"><b-button size="lg" pill variant="warning">Historia</b-button></b-col>
   <b-col lg="4" class="pb-2"><b-button size="lg" pill variant="success">Geografía</b-button></b-col>
    <b-col lg="4" class="pb-2"><b-button size="lg" pill variant="info">Cultura</b-button></b-col>
</b-row>

  </div>
</template>
<style>
.trivia {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
}

</style>