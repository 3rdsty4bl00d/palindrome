<template>
    <div id="user-edit">
        <div class="components text-center">
            <h3>I am the editor</h3>
            <p>Edit me!</p>
            <div class="input-text">
                <input type="text" v-on:input="changeName" placeholder="Your name">
            </div>
            <div class="input-text">
                <input type="number" v-on:input="changeAge" placeholder="Your age">
            </div>
            <div class="input-text">
                <input type="number" v-on:input="changeNumber" placeholder="Your number">
            </div>
        </div>
    </div>
</template>


<script>
    
    import {eventBus} from '../main';
    
    export default {
        methods: {
            changeName: function(event) {
                this.userName = event.target.value;
                eventBus.$emit('userWasChanged', this.userName);
            },
            changeAge: function(event) {
                this.userAge = event.target.value;
                eventBus.$emit('ageWasChanged', this.userAge);
            },
            changeNumber: function(event) {
                this.userNumber = event.target.value;
                eventBus.$emit('numberWasChanged', this.userNumber);
            }
        }
    }
</script>


<style scoped>
    .components {
        background-color: #306BAC;
    }
    .input-text {
        margin: 10px;
    }
</style>