<template>
    <div>
        <h1>Add Objective</h1>
        <label>Target Job Title <input v-model="jobTitle" placeholder="Job Title"></label>
        <label>Objective <input v-model="objective" placeholder="Objective"></label>
    </div>
</template>
<script>
export default {
    name: 'Objective',
    data: () => {
        return {
            jobTitle: "",
            objective: ""
        };
    }
}
</script>
<style>
</style>