<template>
    <div>
        <h1>Add Experience</h1>
        <div v-show="experiences.length < 3">
            <label>Company Name <input v-model="companyName" placeholder="Company Name"></label>
            <label>Job Title <input v-model="roleName" placeholder="Your Role"></label>
            <label>Job Information <input v-model="roleExperience" placeholder="Explain Your Role"></label>
            <label>Start Date <input type="date" v-model="startDate" placeholder="Start Date"></label>
            <label>End Date <input type="date" v-model="endDate" placeholder="End Date"></label>
            <button @click="submitExperience">{{ isEditing ? 'Save' : 'Add another experience' }}</button>
            <button v-if="isEditing" @click="cancelEdit">Cancelar</button>
        </div>
        <ul>
            <li v-for="(experience, index) in experiences" :key="index">
                {{ experience.startDate }} - {{ experience.endDate }}<br/>
                {{ experience.companyName }}, {{ experience.roleName }}<br/>
                {{ experience.roleExperience }}<br/>
                <button v-if="experiences.length < 3" @click="editExperience(index)">Edit</button>
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
            experiences: [],
            isEditing: false,
            editItem: -1,
        };
    },
    methods: {
        submitExperience() {
            if (this.isEditing) {
                this.experiences[this.editItem].companyName = this.companyName;
                this.experiences[this.editItem].roleName = this.roleName;
                this.experiences[this.editItem].roleExperience = this.roleExperience;
                this.experiences[this.editItem].startDate = this.startDate;
                this.experiences[this.editItem].endDate = this.endDate;
                this.editItem = -1;
                this.isEditing = false;
                this.resetFields();
            } else {
                this.addExperience();
            }
        },
        cancelEdit() {
            this.editItem = -1;
            this.isEditing = false;
            this.resetFields();
        },
        editExperience(index) {
            this.isEditing = true;
            this.editItem = index;
            const experience = this.experiences[index];
            this.companyName = experience.companyName;
            this.roleName = experience.roleName;
            this.roleExperience = experience.roleExperience;
            this.startDate = experience.startDate;
            this.endDate = experience.endDate;
        },
        resetFields() {
            this.companyName = "";
            this.roleName = "";
            this.roleExperience = "";
            this.startDate = "";
            this.endDate = "";
        },
        addExperience() {
            this.experiences.push({
                companyName: this.companyName,
                roleName: this.roleName,
                roleExperience: this.roleExperience,
                startDate: this.startDate,
                endDate: this.endDate
            });
            this.resetFields();
        },
        removeExperience(index) {
            this.experiences.splice(index, 1);
        },
    }
}
</script>
<style>
</style>