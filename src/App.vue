<template>
  <div class="legend_div">
    <img src="IHP_PIC_LG.ico" id="legend"/>
  </div>

  <div class="title">
    <h3 class="typing-text">IHP24 REGISTRATION FORM</h3>
  </div>
  

  <div class="form-container">
   
    <form @submit.prevent="submitForm" class="custom-form">
      
      <div class="form-group">
        <label for="fullName">Person Full Name</label><br>
        <input type="text" id="fullName" v-model="formData.fullName" required />
      </div>
      <div class="form-group">
        <label for="gender">Gender</label>
        <label><br>
            <input type="radio" value="Male" v-model="formData.gender" />
            Male
          </label>
          <label>
            <input type="radio" value="Female" v-model="formData.gender" />
            Female
          </label>
      </div>
      <div class="form-group">
        <label for="email">Email</label><br>
        <input type="email" id="email" v-model="formData.email" />
      </div>
      <div class="form-group">
        <label>Do you fellowship with us?</label>
        <div class="radio-options">
          <label>
            <input type="radio" value="yes" v-model="formData.fellowship" />
            Yes
          </label>
          <label>
            <input type="radio" value="no" v-model="formData.fellowship" />
            No
          </label>
        </div>
      </div>
      <div class="form-group">
        <label>How did you get to know about this program?</label>
        <div class="checkbox-options">
          <label>
            <input
              type="checkbox"
              value="Instagram"
              v-model="formData.socialMedia"
            />
            <i class="fa fa-instagram"></i> Instagram
          </label>
          <label>
            <input
              type="checkbox"
              value="Facebook"
              v-model="formData.socialMedia"
            />
            <i class="fa fa-facebook"></i> Facebook
          </label>
          <label>
            <input
              type="checkbox"
              value="Twitter"
              v-model="formData.socialMedia"
            />
            <i class="fa fa-twitter"></i> Twitter
          </label>
          <label>
            <input
              type="checkbox"
              value="Other"
              v-model="formData.socialMedia"
            />
            <i class="fa fa-question-circle"></i> Other
          </label>
        </div>
      </div>
     
      
      <div class="form-group" v-if="formData.socialMedia.includes('Other')">
        <label for="otherText">Please specify how you found out:</label>
        <input type="text" id="otherText" v-model="formData.otherText" />
      </div>
      <div class="form-group">
        <button class="submit-button" type="submit">Submit</button>
      </div>
    </form>
  </div>

</template>

<script>
export default {
  data() {
    return {
      textToType: "IHP24 REGISTRATION FORM",
      typedText: "",
      formData: {
        fullName: '',
        gender: '',
        email: '',
        fellowship: '',
        socialMedia: [],
        otherText: '',
      },
    };
  },
  mounted() {
    this.typeText();
  },
  methods: {
    typeText() {
      let index = 0;
      const typeInterval = 100; // Adjust this to control typing speed

      const typeIntervalId = setInterval(() => {
        if (index < this.textToType.length) {
          this.typedText += this.textToType[index];
          index++;
        } else {
          clearInterval(typeIntervalId);
        }
      }, typeInterval);
    },
  },
    submitForm() {
      // Handle form submission here
      // Redirect to the congratulations Vue component
      this.$router.push({ name: 'Congratulations' });
    },
  };

</script>

<style scoped>
.typing-text {
  white-space: nowrap; /* Prevent text from wrapping */
  overflow: hidden; /* Hide overflowing text */
  border-right: 2px solid transparent; /* Create the typing cursor effect */
  animation: typing 2s steps(20, end), blink-caret 0.5s step-end infinite;
}

@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}

@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: black; /* Adjust the cursor color */
  }
}
.form-container {
  margin-top: none;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}


.custom-form {
  max-width: 400px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background: #fff;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 15px;
}

label {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 12px;
}

input[type="text"],
input[type="email"],
input[type="otherText"],
select {
  width: 90%;
  padding: 10px;
  border: 1px solid #db2f2f;
  border-top: none;
  border-left: none;
  border-right: none;
  border-radius: 5px;
  background: #fff;
  font-size: 14px;
}

.radio-options label {
  display: inline-block;
  margin-right: 20px;
}

.checkbox-options label {
  display: block;
  margin-bottom: 5px;
}

.submit-button {
  display: block;
  width: 100%;
  padding: 10px;
  background: #007BFF; /* Blue color */
  color: #fff;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}

.submit-button:hover {
  background: #0056b3; /* Darker blue on hover */
}
#legend{
  width: 150px;
  height: 75px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);  margin: auto;
  display: flex;
  justify-content: baseline;
  align-items: center;
  transform: matrix3d(180);

}
.title{
  margin-top: none;
  margin-bottom:none ;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: xx-large;
}
.legend_div{
  flex: 1;
  margin: none;
  padding: none;
}

</style>
