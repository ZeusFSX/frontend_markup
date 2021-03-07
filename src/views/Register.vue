<template>
    <div class="container mt-4">
        <div class="row">
            <div class="col-sm-6 mx-auto">
                <form >
                    <div class="form-group">
                        <label for="email">Email address:</label>
                        <input type="email" class="form-control" placeholder="Enter email" id="email">
                    </div>

                    <div class="form-group">
                        <label for="pwd">Password:</label>
                        <input type="password" class="form-control" placeholder="Enter password" id="pwd">
                    </div>

                    <div class="form-group">
                        <label for="pwd">Confirm Password:</label>
                        <input type="password" class="form-control" placeholder="Confirm password" id="pwd">
                    </div>
                    <div class="form-group">
                        <router-link  to="/login"> Already have account? </router-link>
                    </div>
                    <button type="submit" class="btn btn-primary">Submit</button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            username: "",
            password: ""
        }
    }
}
</script>