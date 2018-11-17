<template>
    <div id="user">
        <div class="container">
           <div class="row">
               <div class="col-md-12 text-center">
                   <h1>I am the user</h1>
                   <p>And I'm awesome</p>
               </div>
           </div>
            <div class="row">
                <div class="col-md-6">
                    <app-user-details @userWasChanged="name = $event" @ageWasChanged="age = $event" @numberWasChanged="number = $event"></app-user-details>
                </div>
                <div class="col-md-6">
                    <app-user-edit></app-user-edit>
                </div>
            </div>
            <div class="row">
                <div class="col-md-12">
                    <app-user-crazy></app-user-crazy>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
    import userDetails from './userDetails.vue';
    import userEdit from './userEdit';
    import userCrazy from './userCrazy';
    
    export default {
        components: {
            'appUserDetails': userDetails,
            'appUserEdit': userEdit,
            'appUserCrazy': userCrazy
        }
    }
</script>


<style>
    div.components {
        border: 1px solid black;
        padding: 20px;
        
    }
    #user {
        border: 1px solid black;
        padding: 20px;
        margin: 30px;
        background-color: #98B9F2;
    }
</style>