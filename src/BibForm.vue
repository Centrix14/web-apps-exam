<template>
<p>{{ bib }}</p>
<div class="my-4 mx-2">
  <v-row><v-text-field v-model="bib.name" label="Имя" variant="outlined"></v-text-field></v-row>
  <v-row><v-text-field v-model="bib.author" label="Авторы" variant="outlined"></v-text-field></v-row>
  <v-row><v-text-field v-model="bib.source" label="Источник" variant="outlined"></v-text-field></v-row>
  <v-row>
    <v-text-field v-model="bib.year" class="mr-10" label="Год" variant="outlined"></v-text-field>
    <v-text-field v-model="bib.tags" label="Тэги" variant="outlined"></v-text-field>
  </v-row>
</div>
</template>
<script>
export default {
    props: {
        bib: {
            type: Object,
            requred: true,
        },
    },
    /*computed: {
        bibDataLocal: {
            get() {
                return this.bibData
            },
            
      set(value) {
        this.$emit('update:bibData', value)
      },
    }
  },*/
}
</script>
