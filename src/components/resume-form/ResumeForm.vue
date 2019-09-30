<template>
  <div>
    <PersonalDetails />
    <Objective />
    <Experience />
    <Education />
    <Skills />
    <Interests />
    <button class="resume-form">Submit</button>
  </div>
</template>

<script>
import PersonalDetails from "./form/PersonalDetails.vue";
import Objective from "./form/Objective.vue";
import Experience from "./form/Experience.vue";
import Education from "./form/Education.vue";
import Skills from "./form/Skills.vue";
import Interests from "./form/Interests.vue";

export default {
  name: 'ResumeForm',
  components: {
    PersonalDetails,
    Objective,
    Experience,
    Education,
    Skills,
    Interests
  }
}
</script>

<style>
label {
    display: block;
    margin: 2px 0;
}
.resume-form {
    margin: 20px 0;
}
</style>
