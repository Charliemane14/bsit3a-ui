<template>
    
    <v-card>
      <v-card-title>
        STUDENT LIST
        <v-spacer></v-spacer>
        <v-text-field v-model="search" append-icon="mdi-magnify" label="Search" single-line hide-details></v-text-field>
      </v-card-title>
      
      <v-data-table :headers="headers" :search="search">

        

      </v-data-table> 
    </v-card>
  </template>

  <script>
  export default {
    data() {
      return {
        search: '',
        headers: [
          {
            text: 'Student ID',
            align: 'start',
            sortable: false,
            value: 'StudentID',
          },
          { text: 'LAST NAME', value: 'Lastname' },
          { text: 'FIRST NAME', value: 'Firstname' },
          { text: 'MIDDLE NAME', value: 'Middlename' },
          { text: 'COURSE', value: 'Course' },
          { text: 'SECTION', value: 'Section' },
          { text: '', value: "actions" }
        ],
        
      }
    },
  }
  </script>