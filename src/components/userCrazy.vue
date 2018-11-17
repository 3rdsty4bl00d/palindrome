<template>
    <div id="user-crazy">
        <div class="components text-center">
            <p>Your name in opposite: {{ reverseName() }}</p>
            <p>Your age is: {{ userAge }}</p>
            <p>Your number is: {{ userNumber }} and it is: <span>{{ checkNumber() }}</span> because it's reverse is: {{ reverseNumber() }}</p>
            <p>The number {{ userNumber }} is: <span>{{ oddEvenNumber() }}</span>, and reverse is: <span>{{ reverseOddEvenNumber() }}</span>, because it's reverse is {{ reverseNumber() }}</p>
        </div>
    </div>
</template>


<script>
    
    import {eventBus} from '../main';
    
    export default {
        data: function() {
            return {
                userName: '',
                userAge: '',
                userNumber: ''
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
        },
        methods: {
            reverseName() {
                return this.userName.split("").reverse().join("");
            },
            reverseNumber() {
                return this.userNumber.split("").reverse().join("");  
            },
            checkNumber() {
                var sidhaNumber = this.userNumber;
                var ultoNumber = this.userNumber.split("").reverse().join("");
                if(sidhaNumber === ultoNumber) {
                    return 'Palindrome';
                } else {
                    return 'Not Palindrome';
                }
            },
            oddEvenNumber() {
                var oddEven = this.userNumber;
                var reverseOddEven = this.userNumber.split("").reverse().join("");
                if(oddEven % 2 === 0){
                    return 'Even Number';
                } else {
                    return 'Odd Number';
                }
            },
            reverseOddEvenNumber() {
                var reverseOddEven = this.userNumber.split("").reverse().join("");
                if(reverseOddEven % 2 === 0){
                    return 'Even Number';
                } else {
                    return 'Odd Number';
                }
            }
        }
    }
</script>


<style scoped>
    div.components {
        background-color: aquamarine;
        margin: 20px;
    }
    span {
        background-color: red;
        border: 1px solid black;
        padding: 5px;
    }
</style>