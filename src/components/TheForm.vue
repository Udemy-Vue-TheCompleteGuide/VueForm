<template>
  <form>
    <div class="form-control">
      <label for="user-name">Your Name</label>
      <input id="user-name" name="user-name" type="text" v-model="userName" ref="userName">
    </div>
    <div class="form-control">
      <label for="age">Your Age (Years)</label>
      <input id="age" name="age" type="number" v-model="age"/>
    </div>
    <div class="form-control">
      <label for="referrer">How did you hear about us?</label>
      <select id="referrer" name="referrer" v-model="referrer">
        <option value="google">Google</option>
        <option value="word">Word of mouth</option>
        <option value="newspaper">Newspaper</option>
      </select>
    </div>
    <div class="form-control">
      <h2>What are you interested in?</h2>
      <div>
        <input id="interest-news" name="interest" type="checkbox" value="News" v-model="interest"/>
        <label for="interest-news">News</label>
      </div>
      <div>
        <input id="interest-tutorials" name="interest" type="checkbox" value="Tutorials" v-model="interest"/>
        <label for="interest-tutorials">Tutorials</label>
      </div>
      <div>
        <input id="interest-nothing" name="interest" type="checkbox" value="Nothing" v-model="interest"/>
        <label for="interest-nothing">Nothing</label>
      </div>
    </div>
    <div class="form-control">
      <h2>How do you learn?</h2>
      <div>
        <input id="how-video" name="how" type="radio" value="Video" v-model="how"/>
        <label for="how-video">Video Courses</label>
      </div>
      <div>
        <input id="how-blogs" name="how" type="radio" value="Blogs" v-model="how"/>
        <label for="how-blogs">Blogs</label>
      </div>
      <div>
        <input id="how-other" name="how" type="radio" value="Other" v-model="how"/>
        <label for="how-other">Other</label>
      </div>
    </div>
    <div>
      <button @click.prevent="submitForm">Save Data</button>
    </div>
  </form>
</template>

<script>
export default {
  name: "TheForm",
  data() {
    return {
      userName: 'Marlon',
      age: 37,
      referrer: 'google',
      interest: ['News'],
      how: 'Other'
    };
  },
  methods: {
    submitForm() {
      console.log('User Name by Ref:', this.$refs.userName.value);
      console.log('User Name:', this.userName);

      const userForm = {
        userName: this.userName,
        Age: this.age,
        Referrer: this.referrer,
        Interest: this.interest,
        How: this.how
      };
      console.log('User Form Input:', userForm);
    }
  }
}
</script>

<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 2rem;
  background-color: #ffffff;
}

.form-control {
  margin: 0.5rem 0;
}

label {
  font-weight: bold;
}

h2 {
  font-size: 1rem;
  margin: 0.5rem 0;
}

input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}

select {
  width: auto;
}

input[type='checkbox'],
input[type='radio'] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}

input[type='checkbox'] + label,
input[type='radio'] + label {
  font-weight: normal;
}

button {
  font: inherit;
  border: 1px solid #0076bb;
  background-color: #0076bb;
  color: white;
  cursor: pointer;
  padding: 0.75rem 2rem;
  border-radius: 30px;
}

button:hover,
button:active {
  border-color: #002350;
  background-color: #002350;
}
</style>
