<template>
<v-container fluid>
  <v-app-bar :elevation="0" class="pa-2" color="white" title="BibMan" dark >
    <v-text-field class="mt-5" label="Поиск" variant="outlined"></v-text-field>
    <v-btn class="mx-2" icon="mdi-magnify" variant="tonal" color="orange"/>
    <v-btn
      icon="$plus"
      variant="tonal"
      color="blue"
      @click="cb_add_btn"
      />
  </v-app-bar>
</v-container>
</template>

<script>
export default {
    methods: {
        cb_add_btn() {
            this.$emit("addBib", null)
        }
    }
}
</script>
