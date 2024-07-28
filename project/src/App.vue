<template>
  <b-container class="mt-5" >
    <h6 class="pt-2">Add details</h6>
    <div>
      <label for="datepicker-sm" class="mt-3"> Select a start date</label>
    <b-form-datepicker id="datepicker-sm" size="sm"  class="mb-2"></b-form-datepicker>
  </div>
  <div>
    <b-row>
      <b-col>
        <b-card
          tag="article"
          class="mb-2 mt-3 border-0 custom-card"
        >
          <b-card-text class="custom-card-content">
            <div class="d-flex justify-content-between align-items-center mb-2">
              <p class="mb-0">Select your students</p>
              <b-form-checkbox @change="toggleSelectAll" class="pink-checkbox " v-model="selectAll">Select all students</b-form-checkbox>
            </div>
            <b-row >
              <b-col cols="12" sm="6" md="3"  v-for="student in students" :key="student.id" class="mb-2">
                <div class="d-flex align-items-center">
                  <b-form-checkbox class="pink-checkbox" v-model="student.selected"></b-form-checkbox>
                  <img :src="student.imgSrc" alt="Student Image" class="student-image rounded-circle mr-2">
                  <p class="mb-0 mr-2 ">{{ student.name }}</p>
                </div>
              </b-col>
            </b-row>
          </b-card-text>
        </b-card>
      </b-col>
    </b-row>
   
</div>
  </b-container>
  <div class="absolute-button-container">
        <b-button  class="text-white pink px-5">Continue</b-button>
      </div>
</template>

<script>
export default {
 data() {
    return {
      selectAll: false,
      students: [
        { id: 1, name: 'Student 1', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 2, name: 'Student 2', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 3, name: 'Student 3', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 4, name: 'Student 4', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 5, name: 'Student 5', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 6, name: 'Student 6', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 7, name: 'Student 7', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
        { id: 8, name: 'Student 8', imgSrc: 'https://via.placeholder.com/50', selected: false },
      ],
    };
  },
  methods: {
    toggleSelectAll() {
      this.students.forEach(student => {
        student.selected = this.selectAll;
      });
    },
  },
};

</script>
<style>
.container{
  background-color: rgba(237, 233, 233, 0.877)
}
.pink-checkbox {
  
  border-color: rgb(249, 173, 185) !important;
}
.custom-card {
  max-width: 80rem;
  height: 50vh; 
}
.card-content{
  border: 2px solid rgb(249, 173, 185) !important;

}
.custom-card-content {
  max-height: 50vh;
  overflow-y: scroll; 
  overflow-x: hidden; 
}
.student-image {
  border: 2px solid rgb(249, 173, 185);
  width: 50px;
  height: 50px;
  margin-right: 10px; 
}
.pink {
  background-color: rgb(254, 25, 109)!important;
  border-color: rgb(254, 25, 109)!important;
  border-radius: 25px !important;
}
.position-relative {
  position: relative;
}

.absolute-button-container {
  position: absolute;
  bottom: 8%;
  right: 8%;
}

  @media (max-width: 993px) {
  .absolute-button-container {
    bottom: 20%;
    right: 20%;
  }

  .custom-card {
    height: auto;
  }

  .custom-card-content {
    max-height: 30vh;
  }

  .student-image {
    width: 40px;
    height: 40px;
  }

  .pink-checkbox {
    margin-right: 5px;
  }
}
  @media (max-width: 768px) {
  .absolute-button-container {
    bottom: 10px;
    right: 10px;
  }
}
  @media (max-width: 500px) {
  .absolute-button-container {
    bottom: 30%;
    right: 40%;
  }

  .custom-card {
    height: auto;
  }

  .custom-card-content {
    max-height: 30vh;
  }

  .student-image {
    width: 40px;
    height: 40px;
  }

  .pink-checkbox {
    margin-right: 5px;
  }
}

</style>
