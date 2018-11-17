<template>
    <div id="user-details">
        <div class="components text-center">
            <h3>I've the user details</h3>
            <p>Fill me!</p>
            <p>Your name: {{ userName }}</p>
            <p>Your age: {{ userAge }}</p>
            <p>Your given number: {{ userNumber }}</p>
        </div>
    </div>
</template>


<script>
    
    import {eventBus} from '../main';
    
    export default {
        data: function() {
            return {
                userName: 'Shivam',
                userAge: 22,
                userNumber: 0
            }
        },
        created() {
            eventBus.$on('userWasChanged', (name) => {
                this.userName = name;
            });
            eventBus.$on('ageWasChanged', (age) => {
                this.userAge = age;
            });
            eventBus.$on('numberWasChanged', (number) => {
                this.userNumber = number;
            });
        }
    }
</script>


<style scoped>
    .components {
        background-color: #6F9CEB;
    }
</style>