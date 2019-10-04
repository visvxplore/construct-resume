<template>
    <div>
        <h1>Add Skills</h1>
        <div v-show="skills.length < 10">
            <label>Skill Name <input v-model="skillName" placeholder="Skill Name"></label>
            <label>Skill Rating <input type="number" min="1" max="5" v-model="skillRating" placeholder="Rate out of 5"></label>
            <button @click="addSkill()">Add another skill</button>
        </div>
        <ul>
            <li v-for="(skill, index) in skills" :key="index">
                {{ skill.skillName }} - {{ `${skill.skillRating} Stars` }}<br/>
                <button @click="removeSkill(index)">Remove</button>
            </li> 
        </ul>
    </div>
</template>
<script>
export default {
    name: 'Skills',
    data: () => {
        return {
            skillName: "",
            skillRating: "",
            skills: [],
        };
    },
    methods: {
        addSkill() {
            this.skills.push({
                skillName: this.skillName,
                skillRating: this.skillRating,
            });
            this.skillName = "";
            this.skillRating = "";
        },
        removeSkill(index) {
            this.skills.splice(index, 1);
        }
    },
}
</script>
<style>
</style>