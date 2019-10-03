<template>
    <div>
        <h1>Add Experience</h1>
        <div v-show="experiences.length < 3">
            <label>Company Name <input v-model="companyName" placeholder="Company Name"></label>
            <label>Job Title <input v-model="roleName" placeholder="Your Role"></label>
            <label>Job Information <input v-model="roleExperience" placeholder="Explain Your Role"></label>
            <label>Start Date <input type="date" v-model="startDate" placeholder="Start Date"></label>
            <label>End Date <input type="date" v-model="endDate" placeholder="End Date"></label>
            <button @click="addExperience">Add another experience</button>
        </div>
        <ul>
            <li v-for="(experience, index) in experiences" :key="index">
                {{ experience.startDate }} - {{ experience.endDate }}<br/>
                {{ experience.companyName }}, {{ experience.roleName }}<br/>
                {{ experience.roleExperience }}<br/>
                <button @click="removeExperience(index)">Remove</button>
            </li> 
        </ul>
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
            endDate: "",
            experiences: []
        };
    },
    methods: {
        addExperience() {
            this.experiences.push({
                companyName: this.companyName,
                roleName: this.roleName,
                roleExperience: this.roleExperience,
                startDate: this.startDate,
                endDate: this.endDate
            });
            this.companyName = "";
            this.roleName = "";
            this.roleExperience = "";
            this.startDate = "";
            this.endDate = "";
        },
        removeExperience(index) {
            this.experiences.splice(index, 1);
        }
    }
}
</script>
<style>
</style>