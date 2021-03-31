<template>
    <div>
        <h1>Регистрация</h1>
        <p class="Error">{{Errors.MailError}}</p>
        <p class="Error">{{Errors.PasswordError}}</p>
        <p class="Error">{{Errors.SecondPasswordError}}</p>
        
        <v-text-field class="vInput"
                v-model="Mail"
                label="Введите Ваш Email"
                placeholder="">
            </v-text-field>
        
        <v-text-field class="vInput"
                v-model="Password"
                label="Введите пароль"
                type="Password"
                placeholder="">
            </v-text-field>
        
        <v-text-field class="vInput"
                v-model="SecondPassword"
                label="Повторите пароль"
                type="Password"
                placeholder="">
            </v-text-field>
        
        <v-btn @click="Accept()">Подтвердить</v-btn>
    </div>
</template>

<script>
export default {
    name: 'Step2',
    data: function(){
        return{
            Mail:"",
            Password:"",
            SecondPassword:"",
            Errors:{
                MailError: "",
                SecondPasswordError: "",
                PasswordError: ""
            }
        }
    },
    methods:{
        Accept: function(){
            let count =0;
            if(!this.Mail.includes('@'))
               this.Errors.MailError = "Некорректный Email"
            else{
                this.Errors.MailError = ""
                count = count+1
            }
            if(this.Password == "")
                this.Errors.PasswordError = "Введите пароль"
            else{
                this.Errors.PasswordError = ""
                count = count+1
            }
            if(this.Password != this.SecondPassword)
                this.Errors.SecondPasswordError = "Пароли не совпадают"
            else{
                this.Errors.SecondPasswordError = ""
                count =count+1
            }
            if(count == 3)
                this.$emit('Accept', this.Mail, this.Password) 
        }
    }
}
</script>

<style scoped>
.Error{
    color: red;
}
.vInput{
    width: 50%;
}
</style>