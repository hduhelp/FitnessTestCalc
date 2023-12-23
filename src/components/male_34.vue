<script setup>
    import {ref} from "vue"
    import my_input from "./my_input.vue"
    let heightRef = ref("");
    let weightRef = ref("");
    let vcRef = ref("");
    let sarRef = ref("");
    let jumpRef = ref("");
    let run50Ref = ref("");
    let run1000Min =ref("");
    let run1000Sec = ref("");
    let pullUpRef = ref("");
    const currentRate = ref(0);
    let totalPoints = 0;
    const handleInput=()=>{
    let BMI=Number(weightRef.value)/(Number(heightRef.value)**2)
    let BMIPoints=0
    if (BMI>=28.0){
        BMIPoints=9.0
    }else if(BMI<=17.8){
        BMIPoints=12.0
    }else if(BMI>=24.0&&BMI<27.9){
        BMIPoints=12.0
    }else{
        BMIPoints=15.00   
    }


    let VCPoints = 0;

    if (vcRef.value >= 5140) {
        VCPoints = 15.0;
    } else if (vcRef.value >= 5020 ) {
        VCPoints = 14.25;
    } else if (vcRef.value >= 4900 ) {
        VCPoints = 13.5;
    } else if (vcRef.value >= 4650 ) {
        VCPoints = 12.75;
    } else if (vcRef.value >= 4400 ) {
        VCPoints = 12.0;
    } else if (vcRef.value >= 4280 ) {
        VCPoints = 11.7;
    } else if (vcRef.value >= 4160 ) {
        VCPoints = 11.4;
    } else if (vcRef.value >= 4040 ) {
        VCPoints = 11.1;
    } else if (vcRef.value >= 3920 ) {
        VCPoints = 10.8;
    } else if (vcRef.value >= 3800 ) {
        VCPoints = 10.5;
    } else if (vcRef.value >= 3680 ) {
        VCPoints = 10.2;
    } else if (vcRef.value >= 3560 ) {
        VCPoints = 9.9;
    } else if (vcRef.value >= 3440 ) {
        VCPoints = 9.6;
    } else if (vcRef.value >= 3320 ) {
        VCPoints = 9.3;
    } else if (vcRef.value >= 3200 ) {
        VCPoints = 9.0;
    } else if (vcRef.value >= 3030 ) {
        VCPoints = 7.5;
    } else if (vcRef.value >= 2860 ) {
        VCPoints = 6.0;
    } else if (vcRef.value >= 2690 ) {
        VCPoints = 4.5;
    } else if (vcRef.value >= 2520 ) {
        VCPoints = 3.0;
    } else if (vcRef.value >= 2350 ) {
        VCPoints = 1.5;
    } else {
        VCPoints = 0;
    }




    let sarPoints = 0;

    if (sarRef.value >= 25.1) {
        sarPoints = 10;
    } else if (sarRef.value >= 23.3 ) {
        sarPoints = 9.5;
    } else if (sarRef.value >= 21.5 ) {
        sarPoints = 9.0;
    } else if (sarRef.value >= 19.9 ) {
        sarPoints = 8.5;
    } else if (sarRef.value >= 18.2 ) {
        sarPoints = 8.0;
    } else if (sarRef.value >= 16.8 ) {
        sarPoints = 7.8;
    } else if (sarRef.value >= 15.4 ) {
        sarPoints = 7.6;
    } else if (sarRef.value >= 14.0 ) {
        sarPoints = 7.4;
    } else if (sarRef.value >= 12.6 ) {
        sarPoints = 7.2;
    } else if (sarRef.value >= 11.2 ) {
        sarPoints = 7.0;
    } else if (sarRef.value >= 9.8 ) {
        sarPoints = 6.8;
    } else if (sarRef.value >= 8.4 ) {
        sarPoints = 6.6;
    } else if (sarRef.value >= 7.0 ) {
        sarPoints = 6.4;
    } else if (sarRef.value >= 5.6 ) {
        sarPoints = 6.2;
    } else if (sarRef.value >= 4.2 ) {
        sarPoints = 6.0;
    } else if (sarRef.value >= 3.2 ) {
        sarPoints = 5.0;
    } else if (sarRef.value >= 2.2 ) {
        sarPoints = 4.0;
    } else if (sarRef.value >= 1.2 ) {
        sarPoints = 3.0;
    } else if (sarRef.value >= 0.2 ) {
        sarPoints = 2.0;
    } else if (sarRef.value >= -0.8 ) {
        sarPoints = 1.0;
    } else {
        sarPoints = 0;
    }



    let jumpPoints = 0;

    if (jumpRef.value >= 275) {
        jumpPoints = 10;
    } else if (jumpRef.value >= 270 ) {
        jumpPoints = 9.5;
    } else if (jumpRef.value >= 265 ) {
        jumpPoints = 9.0;
    } else if (jumpRef.value >= 258 ) {
        jumpPoints = 8.5;
    } else if (jumpRef.value >= 250 ) {
        jumpPoints = 8.0;
    } else if (jumpRef.value >= 246 ) {
        jumpPoints = 7.8;
    } else if (jumpRef.value >= 242 ) {
        jumpPoints = 7.6;
    } else if (jumpRef.value >= 238 ) {
        jumpPoints = 7.4;
    } else if (jumpRef.value >= 234 ) {
        jumpPoints = 7.2;
    } else if (jumpRef.value >= 230 ) {
        jumpPoints = 7.0;
    } else if (jumpRef.value >= 226 ) {
        jumpPoints = 6.8;
    } else if (jumpRef.value >= 222 ) {
        jumpPoints = 6.6;
    } else if (jumpRef.value >= 218 ) {
        jumpPoints = 6.4;
    } else if (jumpRef.value >= 214 ) {
        jumpPoints = 6.2;
    } else if (jumpRef.value >= 210 ) {
        jumpPoints = 6.0;
    } else if (jumpRef.value >= 205 ) {
        jumpPoints = 5.0;
    } else if (jumpRef.value >= 200 ) {
        jumpPoints = 4.0;
    } else if (jumpRef.value >= 195 ) {
        jumpPoints = 3.0;
    } else if (jumpRef.value >= 190 ) {
        jumpPoints = 2.0;
    } else if (jumpRef.value >= 185 ) {
        jumpPoints = 1.0;
    } else {
        jumpPoints = 0;
    }


    let run50Points = 0;

    if (run50Ref.value <= 6.6) {
        run50Points = 20.0;
    } else if (run50Ref.value <= 6.7) {
        run50Points = 19.0;
    } else if (run50Ref.value <= 6.8) {
        run50Points = 18.0;
    } else if (run50Ref.value <= 6.9) {
        run50Points = 17.0;
    } else if (run50Ref.value <= 7.0) {
        run50Points = 16.0;
    } else if (run50Ref.value <= 7.2) {
        run50Points = 15.6;
    } else if (run50Ref.value <= 7.4) {
        run50Points = 15.2;
    } else if (run50Ref.value <= 7.6) {
        run50Points = 14.8;
    } else if (run50Ref.value <= 7.8) {
        run50Points = 14.4;
    } else if (run50Ref.value <= 8.0) {
        run50Points = 14.0;
    } else if (run50Ref.value <= 8.2) {
        run50Points = 13.6;
    } else if (run50Ref.value <= 8.4) {
        run50Points = 13.2;
    } else if (run50Ref.value <= 8.6) {
        run50Points = 12.8;
    } else if (run50Ref.value <= 8.8) {
        run50Points = 12.4;
    } else if (run50Ref.value <= 9.0) {
        run50Points = 12.0;
    } else if (run50Ref.value <= 9.2) {
        run50Points = 10.0;
    } else if (run50Ref.value <= 9.4) {
        run50Points = 8.0;
    } else if (run50Ref.value <= 9.6) {
        run50Points = 6.0;
    } else if (run50Ref.value <= 9.8) {
        run50Points = 4.0;
    } else if (run50Ref.value <= 10.0) {
        run50Points = 2.0;
    } else {
        run50Points = 0;
    }


    let run1000Points = 0;
    let run1000Ref = run1000Min.value * 60 + run1000Sec.value;

    if (run1000Ref <= 160) {
        run1000Points = 30.0;
    } else if (run1000Ref <= 163) {
        run1000Points = 29.0;
    } else if (run1000Ref <= 166) {
        run1000Points = 28.0;
    } else if (run1000Ref <= 169) {
        run1000Points = 27.0;
    } else if (run1000Ref <= 172) {
        run1000Points = 26.0;
    } else if (run1000Ref <= 175) {
        run1000Points = 25.0;
    } else if (run1000Ref <= 179) {
        run1000Points = 24.0;
    } else if (run1000Ref <= 183) {
        run1000Points = 23.0;
    } else if (run1000Ref <= 187) {
        run1000Points = 22.0;
    } else if (run1000Ref <= 191) {
        run1000Points = 21.0;
    } else if (run1000Ref <= 195) {
        run1000Points = 20.0;
    } else if (run1000Ref <= 200) {
        run1000Points = 19.0;
    } else if (run1000Ref <= 205) {
        run1000Points = 18.0;
    } else if (run1000Ref <= 212) {
        run1000Points = 17.0;
    } else if (run1000Ref <= 220) {
        run1000Points = 16.0;
    } else if (run1000Ref <= 225) {
        run1000Points = 15.6;
    } else if (run1000Ref <= 230) {
        run1000Points = 15.2;
    } else if (run1000Ref <= 235) {
        run1000Points = 14.8;
    } else if (run1000Ref <= 240) {
        run1000Points = 14.4;
    } else if (run1000Ref <= 245) {
        run1000Points = 14.0;
    } else if (run1000Ref <= 250) {
        run1000Points = 13.6;
    } else if (run1000Ref <= 255) {
        run1000Points = 13.2;
    } else if (run1000Ref <= 260) {
        run1000Points = 12.8;
    } else if (run1000Ref <= 265) {
        run1000Points = 12.4;
    } else if (run1000Ref <= 270) {
        run1000Points = 12.0;
    } else if (run1000Ref <= 290) {
        run1000Points = 10.0;
    } else if (run1000Ref <= 310) {
        run1000Points = 8.0;
    } else if (run1000Ref <= 330) {
        run1000Points = 6.0;
    } else if (run1000Ref <= 350) {
        run1000Points = 4.0;
    } else if (run1000Ref <= 370) {
        run1000Points = 2.0;
    } else {
        run1000Points = 0.0;
    }



    let pullUpPoints = 0;
    if (pullUpRef.value >= 30) {
        pullUpPoints = 20.0;
    } else if (pullUpRef.value == 29) {
        pullUpPoints = 19.0;
    } else if (pullUpRef.value == 28) {
        pullUpPoints = 18.0;
    } else if (pullUpRef.value == 27) {
        pullUpPoints = 17.0;
    } else if (pullUpRef.value == 26) {
        pullUpPoints = 16.0;
    } else if (pullUpRef.value == 25) {
        pullUpPoints = 15.0;
    } else if (pullUpRef.value == 24) {
        pullUpPoints = 14.0;
    } else if (pullUpRef.value == 23) {
        pullUpPoints = 13.0;
    } else if (pullUpRef.value == 22) {
        pullUpPoints = 12.0;
    } else if (pullUpRef.value == 21) {
        pullUpPoints = 11.0;
    } else if (pullUpRef.value == 20) {
        pullUpPoints = 10.0;
    } else if (pullUpRef.value == 19) {
        pullUpPoints = 9.5;
    } else if (pullUpRef.value == 18) {
        pullUpPoints = 9.0;
    } else if (pullUpRef.value == 17) {
        pullUpPoints = 8.5;
    } else if (pullUpRef.value == 16) {
        pullUpPoints = 8.0;
    } else if (pullUpRef.value == 15) {
        pullUpPoints = 7.6;
    } else if (pullUpRef.value == 14) {
        pullUpPoints = 7.2;
    } else if (pullUpRef.value == 13) {
        pullUpPoints = 6.8;
    } else if (pullUpRef.value == 12) {
        pullUpPoints = 6.4;
    } else if (pullUpRef.value == 11) {
        pullUpPoints = 6.0;
    } else if (pullUpRef.value == 10) {
        pullUpPoints = 5.0;
    } else if (pullUpRef.value == 9) {
        pullUpPoints = 4.0;
    } else if (pullUpRef.value == 8) {
        pullUpPoints = 3.0;
    } else if (pullUpRef.value == 7) {
        pullUpPoints = 2.0;
    } else if (pullUpRef.value == 6) {
        pullUpPoints = 1.0;
    } else {
        pullUpPoints = 0;
    }
    totalPoints=BMIPoints+VCPoints+sarPoints+run1000Points+run50Points+pullUpPoints+jumpPoints 
    }
</script>

<template>
        <van-circle
            v-model:current-rate="currentRate"
            :speed="100"
            :text="totalPoints.toString()"
            :color="{
                '0%': '#3fecff',
                '100%': '#6149f6',
            }"
            :rate="totalPoints"
        />
        <my_input
        label="身高(cm)"
        placeholder="请输入身高"
        v-model="heightRef"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="体重(kg)"
        placeholder="请输入体重"
        v-model="weightRef"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="肺活量(ml)"
        placeholder="请输入肺活量"
        v-model="vcRef"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="坐位体前屈(cm)"
        placeholder="请输入坐位体前屈成绩"
        v-model="sarRef"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="立定跳远(cm)"
        placeholder="请输入立定跳远成绩"
        v-model="jumpRef"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="50米(s)"
        placeholder="请输入50米跑成绩"
        v-model="run50Ref"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="1000米(min)"
        placeholder="分"
        v-model="run1000Min"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="1000米(s)"
        placeholder="秒"
        v-model="run1000Sec"
        @input="handleInput"
        @blur="handleInput"
        />
        <my_input
        label="引体向上(次)"
        placeholder="请输入引体向上次数"
        v-model="pullUpRef"
        @input="handleInput"
        @blur="handleInput"
        />
</template>



