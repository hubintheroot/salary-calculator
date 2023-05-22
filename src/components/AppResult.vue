<template>
    <div class="result-container">
        <div class="flex-container">
            <span class="left-text">계산된 월급은</span>
        </div>
        <div class="flex-container"><span class="right-text">
            <span class="salary-info">{{ toStrResult }}</span>원 입니다.</span>
        </div>
    </div>
</template>

<script>
export default {
    props: ['minimumWage', 'selected'],
    data: function(){
        return{
            workingHours: 0,

        }
    },
    methods: {
    },
    computed: {
        toStrResult: function(){
            return this.minimumWage.toLocaleString();
        },
    }
}
</script>

<style>
    @media screen and (max-width: 430px){
        .result-container {
            display: flex;
            justify-content: space-evenly;

            width: 280px; height: 78px;
            margin: 12px auto 0;
            
            border: 1px solid #FFFFFF;
            border-radius: 10px;
            background-color: #5D6283;
        }
        .left-text {
            padding-top: 20px;
            padding-left: 7px;
        }
        .right-text {
            padding-top: 39px;
        }
    }
    .result-container > .flex-container {
        display: flex;
    }
    .salary-info {
        color: #F98011;
    }
    .result-container{
        color: #FFFFFF;
        font-weight: 700;
        font-size: 16px;
        line-height: 19px;

        display: flex;
        justify-content: space-evenly;

        width: 280px; height: 78px;
        margin: 12px auto 0;
        
        border: 1px solid #FFFFFF;
        border-radius: 10px;
        background-color: #5D6283;

    }
    .left-text {
            padding-top: 20px;
            padding-left: 7px;
        }
        .right-text {
            padding-top: 39px;
        }
</style>