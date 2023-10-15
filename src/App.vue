<template>
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
            Instagram
          </label>
          <label>
            <input
              type="checkbox"
              value="Facebook"
              v-model="formData.socialMedia"
            />
            Facebook
          </label>
          <label>
            <input
              type="checkbox"
              value="Twitter"
              v-model="formData.socialMedia"
            />
            Twitter
          </label>
          <label>
            <input
              type="checkbox"
              value="Other"
              v-model="formData.socialMedia"
            />
            Other
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
  methods: {
    submitForm() {
      // Handle form submission here
      // Redirect to the congratulations Vue component
      this.$router.push({ name: 'Congratulations' });
    },
  },
};
</script>

<style scoped>
.form-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Box shadow for the form */
}

.image-legend {
  flex: 1;
  padding: 20px;
}

.image-legend img {
  max-width: 100%;
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
  
}

input[type="text"],
input[type="email"],
select {
  width: 90%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background: #fff;
  font-size: 16px;
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
</style>
