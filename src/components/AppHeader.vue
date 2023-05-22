<template>
    <div class="header-container">
        <span class="title">월급<br/>계산기</span>
        <span class="info">{{ data.year }}년 최저시급은<br/><span class="font-bold font-blue">{{ toStrMinimumWage }}</span>원 입니다.</span>
    </div>
</template>
<script>
export default {
    props: ['data'],
    computed: {
        toStrMinimumWage: function() {
            return this.data.minimumWage.toLocaleString();
        }
    },
}
</script>
<style>
    @media screen and (max-width: 430px){
        .header-container {
            margin: 17px auto 0;
            width: 295px; height: 93px;
            display: flex;
            justify-content: space-evenly;
            align-items: center;
        }
    }
    .title {
        font-size: 32px;
        font-weight: 700;
    }
    .font-bold {
        font-weight: bold;
    }
    .font-blue {
        color: #1F78FF;
    }
    .header-container {
            margin: 17px auto 0;
            width: 295px; height: 93px;
            display: flex;
            justify-content: space-evenly;
            align-items: center;
        }
    
</style>