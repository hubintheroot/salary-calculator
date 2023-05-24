<template>
    <div class="contents-container">
        <app-header v-bind:data="data"/>
        <app-result v-bind:minimum-wage="result"/>
        <app-input v-on:passdata="setData" v-bind:minimum-wage="data.minimumWage"/>
    </div>
</template>
<script>
import AppHeader from './AppHeader.vue';
import AppInput from './AppInput.vue';
import AppResult from './AppResult.vue';
import axios from 'axios'

export default {
    data: function(){
        return{
            data: {
                year: 0,
                minimumWage: 0,
                hourPerDay: 0,
                weeksPerMonth: 0,
                dayOff: 0,
            },
        }
    },
    created() {
        const thisData = this.data
        axios.get('https://api.odcloud.kr/api/15068774/v1/uddi:21d816e5-6c44-4e30-903d-e98e30a4f227?page=1&perPage=1&serviceKey=dTQ%2BBF64rfcdDa7k%2FrroqfVGlkDqVZ%2FNgwEYcWRjvySJ7sHqXyS4PRzeG3nr6KnGGzsVK6JLeeVyXeohTBlEKQ%3D%3D')
            .then(function(response){
                const getData = response.data.data[0]
                thisData.year = getData.연도
                thisData.minimumWage = getData.시간급
                return 0
            })
            .catch((error) => console.log(error))
    },
    computed: {
        result: function() {
            const data = this.data
            const totalWorkingTime = Math.round(data.hourPerDay * data.weeksPerMonth * 4.33) - (data.hourPerDay * data.dayOff);
            const monthlySalary = totalWorkingTime * data.minimumWage;
            return monthlySalary
        }
    },
    components: {
        AppHeader,
        AppInput,
        AppResult,
    },
    methods: {
        setData: function(value){
            this.data.hourPerDay    = value.selectedHours
            this.data.weeksPerMonth = value.selectedDays
            this.data.dayOff        = value.selectedDayoff
        },
    }
}
</script>
<style>
</style>