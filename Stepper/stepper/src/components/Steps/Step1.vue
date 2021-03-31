<template>
    <div>
            <h1>Вход</h1>

            <p class="Error">{{Error}}</p>
            <p class="Error">{{Error.MailError}}</p>
            <v-text-field class="vInput"
                v-model="Email"
                label="Введите Ваш Email"
                >
            </v-text-field>
            <v-text-field class="vInput"
                v-model="Password"
                label="Введите пароль"
                type="Password"
                >
            </v-text-field>
            
            <v-btn @click="Accept()">Далее</v-btn><br><br>
            <v-btn @click="AcceptRegister()">Регистрация</v-btn>
    </div>
    
</template>

<script>
export default {
    name: 'Step1',
    data: function(){
        return{
            Email: "",
            Password: "",
            Error: ""
        }
    },
    methods:{
        Accept: function(){
            
        
            if(!this.Email.includes('@'))
               this.Error = "Некорректный Email"
            else{
                
                this.$emit('Accept',this.Email, this.Password)
            }
            if((this.Email == "")||(this.Password == ""))
                this.Error = "Заполните все поля."
                },


        AcceptRegister: function(){
            this.$emit('AcceptRegister',this.Email, this.Password)
        }
    }
}
</script>

<style scoped>
.vInput{
    width: 50%;
}
.Error{
    color: red;
}
</style>