<template>
    <div>
        <h1>Add Personal Details</h1>
        <label>Name <input v-model="name" placeholder="Name"></label>
        <label>Address <input v-model="address" placeholder="Address"></label>
        <label>City <input v-model="city" placeholder="City"></label>
        <label>Pin Code <input v-model="pin" placeholder="Pin Code"></label>
        <label>Country <input v-model="country" placeholder="Country"></label>
        <label>Email <input type="email" v-model="email" placeholder="Email"></label>
        <label>Phone <input v-model="phone" placeholder="Phone"></label>
    </div>
</template>
<script>
export default {
    name: 'PersonalDetails',
    data: () => {
        return {
            name: "",
            address: "",
            city: "",
            pin: "",
            country: "",
            email: "",
            phone: ""
        };
    }
}
</script>
<style>
</style>