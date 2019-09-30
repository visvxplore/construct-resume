<template>
    <div>
        <h1>Add Experience</h1>
        <label>Company Name <input v-model="companyName" placeholder="Company Name"></label>
        <label>Job Title <input v-model="roleName" placeholder="Your Role"></label>
        <label>Job Information <input v-model="roleExperience" placeholder="Explain Your Role"></label>
        <label>Start Date <input v-model="startDate" placeholder="Start Date"></label>
        <label>End Date <input v-model="endDate" placeholder="End Date"></label>
    </div>
</template>
<script>
export default {
    name: 'Experience',
    data: () => {
        return {
            companyName: "",
            roleName: "",
            roleExperience: "",
            startDate: "",
            endDate: ""
        };
    }
}
</script>
<style>
</style>