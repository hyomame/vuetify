<template>
  <v-container fluid>
    <v-row no-gutters>
      <v-col v-for="n in 3" :key="n" cols="12" md="4" sm="6">
        <v-card class="ma-4" outlined tile>
          <v-card-text>this is {{ n }}th card</v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Home"
};
</script>
