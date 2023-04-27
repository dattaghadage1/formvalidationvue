<template>
    <form id="signup-form" v-on:submit.prevent="submit">
        <div class="row">
            <div class="col-12 form-group">
                <label class="col-form-label col-form-label-lg">Full Name <span class="text-danger">*</span></label>
                <input type="text" v-model.trim="fullname" class="form-control form-control-lg">
                <span class="text-danger" v-for="error in v$.fullname.$errors" :key="error.fullname">
                    plese enter fullname
                </span>
            </div>
            <div class="col-12 form-group">
                <label class="col-form-label col-form-label-lg">Email <span class="text-danger">*</span></label>
                <input type="text" v-model.trim="email" class="form-control form-control-lg">
            </div>
            <span class="text-danger" v-for="error in v$.email.$errors" :key="error.email">
                plese enter email
            </span>
            <div class="col-12 form-group">
                <label class="col-form-label col-form-label-lg">Country <span class="text-danger">*</span></label>
                <select name="" v-model.trim="country" class="form-control form-control-lg">
                    <option disabled value="">Select Country</option>
                    <option value="India">India</option>
                    <option value="USA">USA</option>
                </select>
                <span class="text-danger" v-for="error in v$.country.$errors" :key="error.country">
                    plese select country
                </span>
            </div>
            <div class="col-12 form-group">
                <label class="col-form-label col-form-label-lg">Password <span class="text-danger">*</span></label>
                <input type="text" v-model.trim="password" class="form-control form-control-lg">
                <span class="text-danger" v-for="error in v$.password.$errors" :key="error.password">
                    plese enter password
                </span>
            </div>
            <div class="col-12 form-group text-center">
                <button class="btn vue-btn btn-primary btn-lg col-lg-3 mt-4">Sign Up</button>
            </div>
        </div>
    </form>
</template>
<script>
import { useVuelidate } from '@vuelidate/core'
import { required, email } from '@vuelidate/validators'
export default {
    name: "userFormValidation",
    data() {
        return {
            v$: useVuelidate(),
            fullname: "",
            email: "",
            country: "",
            password: ""
        }
    },
    validations: {
        fullname: { required },
        email: { required },
        country: { required },
        password: { required }
    },
    methods: {
        async submit() {
            const result = await this.v$.$validate();
            if (result) {
                alert("Successfull Login")
            }
        }
    }

}
</script>
<style scoped>
.vue-btn {
    background-color: rgb(4, 110, 75);
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>