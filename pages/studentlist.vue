<template>
    
    <v-card>
      <v-card-title>
        STUDENT LIST
        <v-spacer></v-spacer>
        <v-text-field v-model="search" append-icon="mdi-magnify" label="Search" single-line hide-details></v-text-field>
      </v-card-title>
      
      <v-data-table 
      :headers="headers"
      :items="studentdata" 
      :search="search">

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
            text: 'Student #',
            align: 'start',
            sortable: false,
            value: 'attributes.student_no',
          },
          { text: 'LAST NAME', value: 'attributes.last_name' },
          { text: 'FIRST NAME', value: 'attributes.first_name' },
          { text: 'MIDDLE NAME', value: 'attributes.middle_name' },
          { text: 'COURSE', value: 'attributes.course' },
          { text: 'SECTION', value: 'attributes.section' },
          { text: '', value: "actions" }
        ],
        studentdata: [

        ]
       
      }
    },
    
    methods: {
      getStudentList() {
        this.$axios.get("http://localhost:1337/api/student-lists")
        .then(response => {
          console.log("Success");
          console.log(response.data.data);
          this.studentdata = response.data.data
        })
        .catch(error => {
          console.log("Error")
        })
      }
    },

    mounted() {
      console.log("Auto Run")
      this.getStudentList();

      
    }
  };
  </script>