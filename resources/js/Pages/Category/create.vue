<script setup>
import { reactive } from 'vue'
import { router } from '@inertiajs/vue3'

const form = reactive({
  name: null,
  email: null,
  phone: null,
})

function submit() {
  router.post('/customers.store', form)
}



</script>

<template>
    <div class="container">
        <br>
      <div class="card col-6 offset-3">
        <h5 class="card-header">Create User</h5>
        <div class="card-body">
            <form @click.prevent="submit">
            <div class="mb-3">
                <label for="exampleInputEmail1" class="form-label">Name</label>
                <input type="text" id="name" v-model="form.name" class="form-control"  aria-describedby="emailHelp">
            </div>
            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label">Email</label>
                <input type="email" id="email" v-model="form.email" class="form-control" >
            </div>
            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label">Phone</label>
                <input type="number" id="phone" v-model="phone"  class="form-control" >
            </div>
            <button type="submit" class="btn btn-primary">Submit</button>
            </form>
        </div>
        </div>
    </div>
</template>