<template>
    
    <v-card>
      <v-card-title>
        DASHBOARD
        <v-spacer></v-spacer>
        <v-text-field v-model="search" append-icon="mdi-magnify" label="Search" single-line hide-details></v-text-field>
      </v-card-title>
      
      <v-data-table :headers="headers" :items="StudentData" :search="search">

        <template slot="item.actions" slot-scope="{item}">
          <v-btn style="background-color: red; color: white;"> DELETE</v-btn>
          <v-btn color="green"> EDIT</v-btn>
        </template>

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
            text: 'ID',
            align: 'start',
            sortable: false,
            value: 'StudentID',
          },
          { text: 'FIRST NAME', value: 'Firstname' },
          { text: 'LAST NAME', value: 'Lastname' },
          { text: 'MIDDLE NAME', value: 'Middlename' },
          { text: 'COURSE', value: 'Course' },
          { text: 'YEAR', value: 'Year' },
          { text: '', value: "actions" }
        ],
        StudentData: [
          {
            Firstname: 'Charlie',
            StudentID: '21-00629',
            Lastname: 'Delos Santos',
            Middlename: 'Nacua',
            Course: 'BSIT',
            Year: '3',
          },
          {
            Firstname: 'Ghio',
            StudentID: '21-00611',
            Lastname: 'Pineda',
            Middlename: 'Santos',
            Course: 'BSIT',
            Year: '3',
          },
          {
            Firstname: 'Rs',
            StudentID: '21-00601',
            Lastname: 'Sibug',
            Middlename: 'Joland',
            Course: 'BSIT',
            Year: '3',
          },
          {
            Firstname: 'Sarah',
            StudentID: '21-00602',
            Lastname: 'Nacua',
            Middlename: 'Ds',
            Course: 'BSIT',
            Year: '3',
          },
          {
            Firstname: 'Rolly',
            StudentID: '21-00603',
            Lastname: 'Arellano',
            Middlename: 'Santos',
            Course: 'BSIT',
            Year: '3',
          },
        ],
      }
    },
  }
  </script>