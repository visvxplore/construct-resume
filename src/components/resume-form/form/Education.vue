<template>
    <div>
        <h1>Add Education</h1>
        <label>School <input v-model="school" placeholder="School"></label>
        <label>Degree/Course <input v-model="course" placeholder="Your Degree/Course"></label>
        <label>Job Information <input v-model="roleExperience" placeholder="Explain Your Role"></label>
        <label>Start Date <input type="date" v-model="startDate" placeholder="Start Date"></label>
        <label>End Date <input type="date" v-model="endDate" placeholder="End Date"></label>
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
            endDate: ""
        };
    }
}
</script>
<style>
</style>