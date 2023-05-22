
<template>
    <div class="input-container">

        <div class="left-container flex-container">
            <label for="daily-hours-working" class="select-label">일일 근무시간</label>
            <label for="weekly-days-working" class="select-label">일주 근무일</label>
            <label for="day-off" class="select-label">휴일</label>
        </div>

        <div class="right-container flex-container">
            <select v-model="data.selectedHours" @change="passData" id="daily-hours-working" class="select-container">
                <option value="0" disabled>선택</option>
                <option :key="option" v-for="option in options.hours" :value="option.value">
                    {{ option.text }}
                </option>
            </select>
            
            <select v-model="data.selectedDays" @change="passData" id="weekly-days-working" class="select-container">
                <option value="0" disabled>선택</option>
                <option :key="option" v-for="option in options.days" :value="option.value">
                    {{ option.text }}
                </option>
            </select>
            
            <select v-model="data.selectedDayoff" @change="passData" id="day-off" class="select-container ">
                <option :key="option" v-for="option in options.dayoff" :value="option.value">
                    {{ option.text }}
                </option>
            </select>
        </div>
    </div>
</template>

<script>
export default {
    props: ['minimumWage'],
    methods: {
        passData: function(){
            // TODO 에밋으로 올리는 곳
            if (this.data.selectedHours != 0 && this.data.selectedDays != 0){
                this.$emit('passdata', this.data);
            }
        }
    },
    data() {
        return {
            data: {
            selectedHours: 0,
            selectedDays: 0,
            selectedDayoff: 0,
            },
            options: {
                hours:[
                    {text:'1시간', value: 1},
                    {text:'2시간', value: 2},
                    {text:'3시간', value: 3},
                    {text:'4시간', value: 4},
                    {text:'5시간', value: 5},
                    {text:'6시간', value: 6},
                    {text:'7시간', value: 7},
                    {text:'8시간', value: 8},
                ],
                days: [
                    {text:'1일', value: 1},
                    {text:'2일', value: 2},
                    {text:'3일', value: 3},
                    {text:'4일', value: 4},
                    {text:'5일', value: 5},
                    {text:'6일', value: 6},
                    {text:'7일', value: 7},
                ],
                dayoff: [
                    {text:'0일', value: 0},
                    {text:'1일', value: 1},
                    {text:'2일', value: 2},
                    {text:'3일', value: 3},
                    {text:'4일', value: 4},
                    {text:'5일', value: 5},
                    {text:'6일', value: 6},
                    {text:'7일', value: 7},
                    {text:'8일', value: 8},
                ]
            },
            
        }
    },
}
</script>

<style>
    @media screen and (max-width: 430px){
        .input-container {
            display: flex;
            flex-direction: row;
            justify-content: space-evenly;

            width: 280px; height: 220px;
            margin: 25px auto 0;

            background-color: #FFFFFF;
            border: 1px solid #000000;
            border-radius: 5px;
        }
        .select-container {
            width: 135px; height: 32px;
        }
        
    }

    .input-container > .flex-container {
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
    }

</style>