<template>
<v-app>
  <nav-panel @addBib="openAddDialog"/>
  <v-main>
    <bib-table v-bind:bib="bibList"/>
    <p>{{ bibList }}</p>
  </v-main>

  <add-dialog v-bind:bib="bib" ref="addDialogRef" @bibAdded="addBib"/>
</v-app>
</template>

<script>
import navPanel from './NavPanel.vue'
import bibTable from './BibTable.vue'
import addDialog from './AddDialog.vue'

export default {
    data: () => ({
        bibCount: 3,
        bib: {
            name: "",
            author: "",
            source: "",
            year: "",
            tags: "",
        },
        bibList: [
            {
                id: 1,
                name: 'О вреде оператора GoTo',
                authors: 'Эдсгер Вибе Дейкстра',
                year: 1968,
                source: 'Communications of the ACM',
                tags: '#cleancode #edw',
            },
            {
                id: 2,
                name: 'Архитектура компьютера',
                authors: 'Эндрю Стюарт Танненбаум',
                year: 2017,
                source: 'Питер',
                tags: '#cs #tnb',
            },
        ],
    }),
    methods: {
        openAddDialog() {
            this.$refs.addDialogRef.openDialog()
        },
        
        addBib() {
            this.bibList.push({ id: this.bibCount++, ...this.bib })
        },
    },
    components: {
        navPanel,
        bibTable,
        addDialog,
    },
}
</script>
