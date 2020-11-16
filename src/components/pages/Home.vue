<template>
  <v-container fluid>
    <p class="ma-2">v-row -> v-col*3</p>
    <v-row no-gutters>
      <v-col v-for="n in 3" :key="n" cols="6" md="4">
        <v-card class="ma-2" outlined tile>
          <v-card-title>v-col {{ n }}</v-card-title>
        </v-card>
      </v-col>
    </v-row>
    <p class="ma-2">v-row -> v-col*2 -> v-row*2 -> v-col</p>
    <v-row no-gutters>
      <v-col v-for="n in 2" :key="n" cols="12" md="6">
        <v-card class="ma-2" outlined tile>
          <v-card-title>v-col {{ n }}</v-card-title>
          <v-row v-for="n in 2" :key="n" no-gutters>
            <v-col cols="12">
              <v-card class="ma-2" outlined tile>
                <v-card-title>v-col {{ text[n - 1] }}</v-card-title>
              </v-card>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
    <p class="ma-2">v-row -> v-col*2 -> v-row -> v-col*2</p>
    <v-row no-gutters>
      <v-col v-for="n in 2" :key="n" cols="12" md="6">
        <v-card class="ma-2" outlined tile>
          <v-card-title>v-col {{ n }}</v-card-title>
          <v-row no-gutters>
            <v-col v-for="n in 2" :key="n" cols="12">
              <v-card class="ma-2" outlined tile>
                <v-card-title>v-col {{ text[n - 1] }}</v-card-title>
              </v-card>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      text: ["top", "bottom"]
    };
  }
};
</script>
