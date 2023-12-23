<script setup>
    import {ref} from "vue"
    import my_input from "./my_input.vue"
    import text1000 from "./text1000.vue"
    let heightRef = ref("");
    let weightRef = ref("");
    let vcRef = ref("");
    let sarRef = ref("");
    let jumpRef = ref("");
    let run50Ref = ref("");
    let run1000Min = ref("");
    let run1000Sec = ref("");
    let pullUpRef = ref("");
    const currentRate = ref(0);
    let totalPoints = 0;
    const handleInput=()=>{
    let BMI=Number(weightRef.value)/(Number((heightRef.value)/100)**2)
    BMI=BMI.toFixed(3)
    let BMIPoints = 0.0;
    if (heightRef.value === "" || weightRef.value === ""){
        BMIPoints = 0.0;
    }
    if (isNaN(heightRef.value) || isNaN(weightRef.value)){
        BMIPoints = 0.0;
    }
    if (BMI>=28.0){
        BMIPoints=9.0
    }else if(BMI>=24.0){
        BMIPoints=80
    }else if(BMI<17.9){
        BMIPoints=12.0
    }else{
        BMIPoints=15.0
    }

    let VCPoints = 0;
    if (vcRef.value === "" || isNaN(vcRef.value)){
        VCPoints = 0.0;
    }
    if (vcRef.value >= 5040) {
        VCPoints = 15.0;
    } else if (vcRef.value >= 4920 ) {
        VCPoints = 14.25;
    } else if (vcRef.value >= 4800 ) {
        VCPoints = 13.5;
    } else if (vcRef.value >= 4550 ) {
        VCPoints = 12.75;
    } else if (vcRef.value >= 4300 ) {
        VCPoints = 12.0;
    } else if (vcRef.value >= 4180 ) {
        VCPoints = 11.7;
    } else if (vcRef.value >= 4060 ) {
        VCPoints = 11.4;
    } else if (vcRef.value >= 3940 ) {
        VCPoints = 11.1;
    } else if (vcRef.value >= 3820 ) {
        VCPoints = 10.8;
    } else if (vcRef.value >= 3700 ) {
        VCPoints = 10.5;
    } else if (vcRef.value >= 3580 ) {
        VCPoints = 10.2;
    } else if (vcRef.value >= 3460 ) {
        VCPoints = 9.9;
    } else if (vcRef.value >= 3340 ) {
        VCPoints = 9.6;
    } else if (vcRef.value >= 3220 ) {
        VCPoints = 9.3;
    } else if (vcRef.value >= 3100 ) {
        VCPoints = 9.0;
    } else if (vcRef.value >= 2940 ) {
        VCPoints = 7.5;
    } else if (vcRef.value >= 2780 ) {
        VCPoints = 6.0;
    } else if (vcRef.value >= 2620 ) {
        VCPoints = 4.5;
    } else if (vcRef.value >= 2460 ) {
        VCPoints = 3.0;
    } else if (vcRef.value >= 2300 ) {
        VCPoints = 1.5;
    } else {
        VCPoints = 0;
    }




    let sarPoints = 0;
    if (sarRef.value === "" || isNaN(sarRef.value)){
        sarPoints = 0;
    }

    if (sarRef.value >= 24.9) {
        sarPoints = 10;
    } else if (sarRef.value >= 23.1 ) {
        sarPoints = 9.5;
    } else if (sarRef.value >= 21.3 ) {
        sarPoints = 9.0;
    } else if (sarRef.value >= 19.5 ) {
        sarPoints = 8.5;
    } else if (sarRef.value >= 17.7 ) {
        sarPoints = 8.0;
    } else if (sarRef.value >= 16.3 ) {
        sarPoints = 7.8;
    } else if (sarRef.value >= 14.9 ) {
        sarPoints = 7.6;
    } else if (sarRef.value >= 13.5 ) {
        sarPoints = 7.4;
    } else if (sarRef.value >= 12.1 ) {
        sarPoints = 7.2;
    } else if (sarRef.value >= 10.7 ) {
        sarPoints = 7.0;
    } else if (sarRef.value >= 9.3 ) {
        sarPoints = 6.8;
    } else if (sarRef.value >= 7.9 ) {
        sarPoints = 6.6;
    } else if (sarRef.value >= 6.5 ) {
        sarPoints = 6.4;
    } else if (sarRef.value >= 5.1 ) {
        sarPoints = 6.2;
    } else if (sarRef.value >= 3.7 ) {
        sarPoints = 6.0;
    } else if (sarRef.value >= 2.7 ) {
        sarPoints = 5.0;
    } else if (sarRef.value >= 1.7 ) {
        sarPoints = 4.0;
    } else if (sarRef.value >= 0.7 ) {
        sarPoints = 3.0;
    } else if (sarRef.value >= -0.3 ) {
        sarPoints = 2.0;
    } else if (sarRef.value >= -1.3 ) {
        sarPoints = 1.0;
    }else {
        sarPoints = 0;
    }



    let jumpPoints = 0;
    if (jumpRef === "" || isNaN(jumpRef === "")){
        jumpPoints = 0;
    }

    if (jumpRef.value >= 273) {
        jumpPoints = 10;
    } else if (jumpRef.value >= 268 ) {
        jumpPoints = 9.5;
    } else if (jumpRef.value >= 263 ) {
        jumpPoints = 9.0;
    } else if (jumpRef.value >= 256 ) {
        jumpPoints = 8.5;
    } else if (jumpRef.value >= 248 ) {
        jumpPoints = 8.0;
    } else if (jumpRef.value >= 244 ) {
        jumpPoints = 7.8;
    } else if (jumpRef.value >= 240 ) {
        jumpPoints = 7.6;
    } else if (jumpRef.value >= 236 ) {
        jumpPoints = 7.4;
    } else if (jumpRef.value >= 232 ) {
        jumpPoints = 7.2;
    } else if (jumpRef.value >= 228 ) {
        jumpPoints = 7.0;
    } else if (jumpRef.value >= 224 ) {
        jumpPoints = 6.8;
    } else if (jumpRef.value >= 220 ) {
        jumpPoints = 6.6;
    } else if (jumpRef.value >= 216 ) {
        jumpPoints = 6.4;
    } else if (jumpRef.value >= 212 ) {
        jumpPoints = 6.2;
    } else if (jumpRef.value >= 208 ) {
        jumpPoints = 6.0;
    } else if (jumpRef.value >= 203 ) {
        jumpPoints = 5.0;
    } else if (jumpRef.value >= 198 ) {
        jumpPoints = 4.0;
    } else if (jumpRef.value >= 193 ) {
        jumpPoints = 3.0;
    } else if (jumpRef.value >= 188 ) {
        jumpPoints = 2.0;
    } else if (jumpRef.value >= 183 ) {
        jumpPoints = 1.0;
    } else {
        jumpPoints = 0;
    }


    let run50Points = 0;
    if (run50Ref.value === "" || run50Ref.value === ""){
        run50Points = 0
    }

    if (run50Ref.value <= 6.7) {
        run50Points = 20.0;
    } else if (run50Ref.value <= 6.8) {
        run50Points = 19.0;
    } else if (run50Ref.value <= 6.9) {
        run50Points = 18.0;
    } else if (run50Ref.value <= 7.0) {
        run50Points = 17.0;
    } else if (run50Ref.value <= 7.1) {
        run50Points = 16.0;
    } else if (run50Ref.value <= 7.3) {
        run50Points = 15.6;
    } else if (run50Ref.value <= 7.5) {
        run50Points = 15.2;
    } else if (run50Ref.value <= 7.7) {
        run50Points = 14.8;
    } else if (run50Ref.value <= 7.9) {
        run50Points = 14.4;
    } else if (run50Ref.value <= 8.1) {
        run50Points = 14.0;
    } else if (run50Ref.value <= 8.3) {
        run50Points = 13.6;
    } else if (run50Ref.value <= 8.5) {
        run50Points = 13.2;
    } else if (run50Ref.value <= 8.7) {
        run50Points = 12.8;
    } else if (run50Ref.value <= 8.9) {
        run50Points = 12.4;
    } else if (run50Ref.value <= 9.1) {
        run50Points = 12.0;
    } else if (run50Ref.value <= 9.3) {
        run50Points = 10.0;
    } else if (run50Ref.value <= 9.5) {
        run50Points = 8.0;
    } else if (run50Ref.value <= 9.7) {
        run50Points = 6.0;
    } else if (run50Ref.value <= 9.9) {
        run50Points = 4.0;
    } else if (run50Ref.value <= 10.1) {
        run50Points = 2.0;
    } else {
        run50Points = 0;
    }


    let run1000Points = 0;
    let run1000Ref = Number(run1000Min.value) * 60 + Number(run1000Sec.value);
    if (run1000Sec.value === "" || run1000Min.value === ""){
        run1000Points = 0;
    }
    if(isNaN(run1000Sec.value)||isNaN(run1000Min)){
        run1000Points = 0;
    }

    if (run1000Ref <= 162) {
        run1000Points = 30.0;
    } else if (run1000Ref <= 165) {
        run1000Points = 29.0;
    } else if (run1000Ref <= 168) {
        run1000Points = 28.0;
    } else if (run1000Ref <= 171) {
        run1000Points = 27.0;
    } else if (run1000Ref <= 174) {
        run1000Points = 26.0;
    } else if (run1000Ref <= 177) {
        run1000Points = 25.0;
    } else if (run1000Ref <= 181) {
        run1000Points = 24.0;
    } else if (run1000Ref <= 185) {
        run1000Points = 23.0;
    } else if (run1000Ref <= 189) {
        run1000Points = 22.0;
    } else if (run1000Ref <= 193) {
        run1000Points = 21.0;
    } else if (run1000Ref <= 197) {
        run1000Points = 20.0;
    } else if (run1000Ref <= 202) {
        run1000Points = 19.0;
    } else if (run1000Ref <= 207) {
        run1000Points = 18.0;
    } else if (run1000Ref <= 214) {
        run1000Points = 17.0;
    } else if (run1000Ref <= 222) {
        run1000Points = 16.0;
    } else if (run1000Ref <= 227) {
        run1000Points = 15.6;
    } else if (run1000Ref <= 232) {
        run1000Points = 15.2;
    } else if (run1000Ref <= 237) {
        run1000Points = 14.8;
    } else if (run1000Ref <= 242) {
        run1000Points = 14.4;
    } else if (run1000Ref <= 247) {
        run1000Points = 14.0;
    } else if (run1000Ref <= 252) {
        run1000Points = 13.6;
    } else if (run1000Ref <= 257) {
        run1000Points = 13.2;
    } else if (run1000Ref <= 262) {
        run1000Points = 12.8;
    } else if (run1000Ref <= 267) {
        run1000Points = 12.4;
    } else if (run1000Ref <= 272) {
        run1000Points = 12.0;
    } else if (run1000Ref <= 292) {
        run1000Points = 10.0;
    } else if (run1000Ref <= 312) {
        run1000Points = 8.0;
    } else if (run1000Ref <= 332) {
        run1000Points = 6.0;
    } else if (run1000Ref <= 352) {
        run1000Points = 4.0;
    } else if (run1000Ref <= 372) {
        run1000Points = 2.0;
    } else {
        run1000Points = 0.0;
    }



    let pullUpPoints = 0;
    if (pullUpRef.value === ""||pullUpRef.value === ""){
        pullUpPoints = 0;
    }
    if (pullUpRef.value >= 29) {
        pullUpPoints = 20.0;
    } else if (pullUpRef.value == 28) {
        pullUpPoints = 19.0;
    } else if (pullUpRef.value == 27) {
        pullUpPoints = 18.0;
    } else if (pullUpRef.value == 26) {
        pullUpPoints = 17.0;
    } else if (pullUpRef.value == 25) {
        pullUpPoints = 16.0;
    } else if (pullUpRef.value == 24) {
        pullUpPoints = 15.0;
    } else if (pullUpRef.value == 23) {
        pullUpPoints = 14.0;
    } else if (pullUpRef.value == 22) {
        pullUpPoints = 13.0;
    } else if (pullUpRef.value == 21) {
        pullUpPoints = 12.0;
    } else if (pullUpRef.value == 20) {
        pullUpPoints = 11.0;
    } else if (pullUpRef.value == 19) {
        pullUpPoints = 10.0;
    } else if (pullUpRef.value == 18) {
        pullUpPoints = 9.5;
    } else if (pullUpRef.value == 17) {
        pullUpPoints = 9.0;
    } else if (pullUpRef.value == 16) {
        pullUpPoints = 8.5;
    } else if (pullUpRef.value == 15) {
        pullUpPoints = 8.0;
    } else if (pullUpRef.value == 14) {
        pullUpPoints = 7.6;
    } else if (pullUpRef.value == 13) {
        pullUpPoints = 7.2;
    } else if (pullUpRef.value == 12) {
        pullUpPoints = 6.8;
    } else if (pullUpRef.value == 11) {
        pullUpPoints = 6.4;
    } else if (pullUpRef.value == 10) {
        pullUpPoints = 6.0;
    } else if (pullUpRef.value == 9) {
        pullUpPoints = 5.0;
    } else if (pullUpRef.value == 8) {
        pullUpPoints = 4.0;
    } else if (pullUpRef.value == 7) {
        pullUpPoints = 3.0;
    } else if (pullUpRef.value == 6) {
        pullUpPoints = 2.0;
    } else if (pullUpRef.value == 5) {
        pullUpPoints = 1.0;
    } else {
        pullUpPoints = 0;
    }

    totalPoints=BMIPoints+VCPoints+sarPoints+run1000Points+run50Points+pullUpPoints+jumpPoints 
    }
    const onClickRight=()=>{
        heightRef = "";
        weightRef = "";
        vcRef = "";
        sarRef = "";
        jumpRef = "";
        run50Ref = "";
        run1000Min ="";
        run1000Sec = "";
        pullUpRef = "";
        totalPoints = 0;
        handleInput()
    }
</script>

<template>
    <div class="points">
        <div style="padding-top: 10px;">
            <van-circle
                v-model:current-rate="currentRate"
                :speed="100"
                :text="totalPoints.toString()"
                :stroke-width="60"
                :color="{
                    '0%': '#3fecff',
                    '100%': '#6149f6',
                }"
                :rate="totalPoints"
            />
        </div>
    </div>
        <van-nav-bar
            title="总成绩"
            class="points"
            right-text="重置"
            @click-right="onClickRight"
        />
        <my_input
        label="身高(cm)"
        placeholder="请输入身高"
        v-model="heightRef"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/bmi.jpg"
        />
        <my_input
        label="体重(kg)"
        placeholder="请输入体重"
        v-model="weightRef"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/bmi.jpg"
        />
        <my_input
        label="肺活量(ml)"
        placeholder="请输入肺活量"
        v-model="vcRef"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/vc.jpg"
        />
        <my_input
        label="坐位体前屈(cm)"
        placeholder="请输入坐位体前屈成绩"
        v-model="sarRef"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/sar.jpg"
        />
        <my_input
        label="立定跳远(cm)"
        placeholder="请输入立定跳远成绩"
        v-model="jumpRef"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/jump.jpg"
        />
        <my_input
        label="50米(s)"
        placeholder="请输入50米跑成绩"
        v-model="run50Ref"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/run50.jpg"
        />
        <text1000
        label="1000米(min)"
        placeholder="分"
        v-model:min="run1000Min"
        v-model:sec="run1000Sec"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/run800_1000.jpg"
        /> 
        <my_input
        label="引体向上(次)"
        placeholder="请输入引体向上次数"
        v-model="pullUpRef"
        @input="handleInput"
        @blur="handleInput"
        />
        <!-- <my_input
        label="1000米(min)"
        placeholder="分"
        v-model="run1000Min"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/run800_1000.jpg"
        /> 
        <my_input
        label="1000米(s)"
        placeholder="秒"
        v-model="run1000Sec"
        @input="handleInput"
        @blur="handleInput"
        mySrc="../assets/run800_1000.jpg"
        /> -->
</template>
<style>
    .points{
        text-align: center;
        background-color: #d9ecff;
    }
</style>


<!-- 目前的问题如下：
最新的都在male_12里，其他三个以mael_12为主
重置按钮
分数提前显示

-->


