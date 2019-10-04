<template>
<div>
    <h1>Add Education</h1>

    <label>School
        <input v-model="school" placeholder="School">
    </label>

    <label>Degree/Course
        <input v-model="course" placeholder="Your Degree/Course">
    </label>

    <label>Job Information
        <input v-model="roleExperience" placeholder="Explain Your Role">
    </label>

    <label>Start Date
        <input type="date" v-model="startDate" placeholder="Start Date">
    </label>

    <label>End Date
        <input type="date" v-model="endDate" placeholder="End Date">
    </label>

    <button @click="addEducation" v-if="educations.length < 1">Add Education</button>
    <button @click="addEducation" v-else>Add Another Education</button>
    <ul>
        <li v-for="(education, index) in educations" :key="index">
            {{ education.startDate }} - {{ education.endDate }}<br />
            {{ education.school }}, {{ education.course }}<br />
            {{ education.roleExperience }}<br />
            <button @click="removeEducation(index)">Remove</button>
        </li>
    </ul>

</div>
</template>

<script>
export default {
    name: 'Education',
    data: () => {
        return {
            school: "",
            course: "",
            roleExperience: "",
            startDate: "",
            endDate: "",
            educations: []
        };
    },
    methods: {
        addEducation() {
            let data = {
                school: this.school,
                course: this.course,
                roleExperience: this.roleExperience,
                startDate: this.startDate,
                endDate: this.endDate,
            }
            this.educations.push(data);
            this.school = ""
            this.course = ""
            this.roleExperience = ""
            this.startDate = ""
            this.endDate = ""
        },
        removeEducation(index) {
            this.educations.splice(index, 1)
        }
    }
}
</script>

<style>
</style>
