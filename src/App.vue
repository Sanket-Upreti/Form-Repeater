<template>
<div>
    <app-header> </app-header>
  <div id="app">
    <div class="top-div">
        <h1>{{ repeatingForm }}</h1>
      </div>
      <div class="mid-div">
        <h3>{{ department }}</h3>
        <div class="forForm">
          <form v-for="(formValue, index) in formValues" :key="index.id">
            <div class="for-name">
              <label>Name </label>
              <input
                type="text"
                class="text"
                v-model="formValue.name"
                required
              />
            </div>
            <div class="for-name">
              <label>Joined Date</label>
              <input
                type="text"
                class="text"
                v-model="formValue.date"
              />
            </div>
            <div class="for-name">
              <label>Job Description</label>
              <textarea v-model="formValue.content"></textarea>
            </div>
            <div class="for-name-ii">
              <label>Tier</label>
              <br />
              <input
                type="radio"
                value="Junior"
                v-model="formValue.tiers"
              />
              <label>Junior</label>
              <input
                type="radio"
                value="Senior"
                v-model="formValue.tiers"
              />
              <label>Senior</label>
            </div>
            <div class="for-name-ii">
              <label>Language</label>
              <br />
              <input
                type="checkbox"
                value="English"
                v-model="formValue.englishLang"
              />
              <label>English</label>
              <input
                type="checkbox"
                value="French"
                v-model="formValue.frenchLang"
              />
              <label>French</label>
            </div>
            <div class="for-name">
              <label>Department</label>
              <select v-model="formValue.Department">
                <option
                  v-for="Department in formValue.Departments"
                  :key="Department"
                  >{{ Department }}</option
                >
              </select>
            </div>
            <div class="redButton">
              <button type="button" @click="delButton(index)">Delete</button>
            </div>
          </form>
          <hr />
          <div class="add-form">
            <button @click="addForm()">Add</button>
          </div>
          <div id="preview">
            <h3><strong>Preview Form</strong></h3>
            <pre>
              {{ $data }}
            </pre>
          </div>
        </div>
      </div>
    </div>
    <app-footer> </app-footer>

    </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    "app-header": Header,
    "app-footer": Footer,
  },
  data: function(){
    return{
       department: "Human Resource Management",
        repeatingForm: "Repeating Forms",
    formValues: [
      {
        name : "",
         date: "",
        content: "",
        tiers: "",
        englishLang: "",
        frenchLang: "",
        Department: "",
        Departments: ["Marketing", "Creative", "Development"],
       
      },      
    ],
    }
  },
   methods: {
    addForm: function() {
      this.formValues.push({ name : "",
         date: "",
        content: "",
        tiers: "",
        englishLang: "",
        frenchLang: "",
        Department: "",
        Departments: ["Marketing", "Creative", "Development"],
        });
    },
    delButton: function(id) {
      this.formValues.splice(id, 1);
    },
  },
};
</script>

<style scoped>
* {
  margin: 0 0;
  padding: 0 0;
  box-sizing: border-box;
}

.app-content {
  margin-top: 2%;
  margin-bottom: 2%;
}

.mid-div {
  padding: 10px 10px;
  border: 1px solid #e7505a;
}

h1 {
  background: #e7505a;
  color: white;
  font-size: 20px;
  padding: 5px;
}

h3 {
  text-transform: uppercase;
  font-weight: 800;
}

hr {
  width: 100%;
  height: 1px;
  background: silver;
  margin-top: 2%;
}

#preview {
  padding: 10px 20px;
  border: 1px solid black;
  margin: 30px 0;
}

form {
  display: flex;
  margin-top: 2%;
  justify-content: space-evenly;
}

.for-name {
  max-width: 150px;
  display: block;
}

input[type="radio"] {
  margin: 0px 10px;
}

input[type="checkbox"] {
  margin: 0px 10px;
}

label {
  line-height: 24px;
}

.redButton button {
  position: relative;
  top: 25%;
  left: -40%;
  background: #e7505a;
  border: 1px solid #e7505a;
  color: aliceblue;
  cursor: pointer;
  padding: 8px 8px;
}

.add-form button {
  background: #36c6d3;
  border: 1px solid #36c6d3;
  color: aliceblue;
  cursor: pointer;
  padding: 8px 8px;
  margin-top: 2%;
}

.add-form button:hover {
  filter: brightness(90%);
}
</style>>
</style>
