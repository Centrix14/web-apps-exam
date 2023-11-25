<template>
<v-container>
  <v-data-table fixed-header>
    <thead>
      <tr>
        <th class="text-left">#</th>
        <th class="text-left">Имя</th>
        <th class="text-left">Авторы</th>
        <th class="text-left">Год</th>
        <th class="text-left">Источник</th>
        <th class="text-left">Тэги</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in bib" :key="item.name">
        <td>{{ item.id }}</td>
        <td>{{ item.name }}</td>
        <td>{{ item.authors }}</td>
        <td>{{ item.year }}</td>
        <td>{{ item.source }}</td>
        <td>{{ item.tags }}</td>
      </tr>
    </tbody>
  </v-data-table>
</v-container>
</template>

<script>
export default {
    props: {
        bib: {
            type: Array,
            required: true
        },
    },
}
</script>
