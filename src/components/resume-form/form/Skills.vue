<template>
    <div>
        <h1>Add Skills</h1>
        <label>Skill Name <input v-model="skillName" placeholder="Skill Name"></label>
        <label>Skill Rating <input type="number" min="1" max="5" v-model="skillRating" placeholder="Rate out of 5"></label>
    </div>
</template>
<script>
export default {
    name: 'Skills',
    data: () => {
        return {
            skillName: "",
            skillRating: ""
        };
    }
}
</script>
<style>
</style>