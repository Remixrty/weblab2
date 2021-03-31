<template>
    <div>
        <h1>Ваши данные</h1>
        <p>Email: {{Person.Email}}</p>
        <p>Пароль: {{Person.Password}}</p>
    </div>
</template>

<script>
export default {
    name: 'Step3',
    props:['Person'],
    data: function(){
        
    }
}
</script>

<style scoped>
</style>