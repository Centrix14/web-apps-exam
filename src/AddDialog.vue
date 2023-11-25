<template>
<v-dialog v-model="addDialog" width="500">
  <template v-slot:default="{ isActive }">
    <v-card title="Добавить запись">
      <v-card-text>
        <bibForm v-bind:bib="bib"></bibForm>
      </v-card-text>
      
      <v-card-actions>
        <v-spacer></v-spacer>
        
        <v-btn text="Отмена" @click="isActive.value = false"></v-btn>
        <v-btn text="Добавить" @click="ok_bttn_cb"></v-btn>
      </v-card-actions>
    </v-card>
  </template>
</v-dialog>
</template>

<script>
import bibForm from './BibForm.vue'

export default {
    props: {
        bib: {
            type: Object,
            required: true,
        },
    },
    data: () => ({
        addDialog: false,
        bibData: {},
    }),
    
    components: { bibForm },
    methods: {
        openDialog() {
            this.addDialog = true
        },
        
        ok_bttn_cb() {
            this.$emit('bibAdded', null)
        }
    },
}
</script>
