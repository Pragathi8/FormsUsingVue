<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Enter details:</h1>
                    <hr>
                    <app-full-name v-model='fullName'></app-full-name>
                    <div class="form-group">
                        <label for="email">Mail:</label>
                        <input
                                type="text"
                                id="email"
                                class="form-control" required
                                v-model="mailId">
                    </div>
                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input
                                type="password"
                                id="password"
                                class="form-control" required
                                v-model="password">
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                    <label for="yes">
                        <input
                                type="radio"
                                id="yes"
                                value="Yes" 
                                v-model="storeData"> Yes
                    </label>
                    <label for="no">
                        <input
                                type="radio"
                                id="no"
                                value="No"
                                v-model="storeData"> No
                    </label>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            class="btn btn-primary"
                            @click.prevent="submitted">Submit!
                    </button>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{fullName}}</p>
                        <p>Mail: {{mailId}}</p>
                        <p>Password: {{password}}</p>
                        <p>Store in Database?: {{storeData}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './FullName.vue';
    export default {
        data() {
            return {
                    // firstName: '',
                    // lastName: '',
                    fullName: '',
                    mailId: '',
                    password: '',
                    storeData: 'Yes',
                    isSubmitted: false
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true;
            }
        },
        components: {
            appFullName: FullName
        }
    }
</script>

<style>
</style>
