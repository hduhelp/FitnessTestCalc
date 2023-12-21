<script setup>
    import {ref} from "vue"
    import my_input from "./my_input.vue"
    let heightRef = ref("");
    let weightRef = ref("");
    let vcRef = ref("");
    let sarRef = ref("");
    let jumpRef = ref("");
    let run50Ref = ref("");
    let run800Min =ref("");
    let run800Sec = ref("");
    let sitUpRef = ref("");
    const currentRate = ref(0);
    let totalPoints=0
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

    if (vcRef.value >= 3450) {
        VCPoints = 15.0;
    } else if (vcRef.value >= 3400 ) {
        VCPoints = 14.25;
    } else if (vcRef.value >= 3350 ) {
        VCPoints = 13.5;
    } else if (vcRef.value >= 3200 ) {
        VCPoints = 12.75;
    } else if (vcRef.value >= 3050 ) {
        VCPoints = 12.0;
    } else if (vcRef.value >= 2950 ) {
        VCPoints = 11.7;
    } else if (vcRef.value >= 2850 ) {
        VCPoints = 11.4;
    } else if (vcRef.value >= 2750 ) {
        VCPoints = 11.1;
    } else if (vcRef.value >= 2650 ) {
        VCPoints = 10.8;
    } else if (vcRef.value >= 2550 ) {
        VCPoints = 10.5;
    } else if (vcRef.value >= 2450 ) {
        VCPoints = 10.2;
    } else if (vcRef.value >= 2350 ) {
        VCPoints = 9.9;
    } else if (vcRef.value >= 2250 ) {
        VCPoints = 9.6;
    } else if (vcRef.value >= 2150 ) {
        VCPoints = 9.3;
    } else if (vcRef.value >= 2050 ) {
        VCPoints = 9.0;
    } else if (vcRef.value >= 2010 ) {
        VCPoints = 7.5;
    } else if (vcRef.value >= 1970 ) {
        VCPoints = 6.0;
    } else if (vcRef.value >= 1930 ) {
        VCPoints = 4.5;
    } else if (vcRef.value >= 1890 ) {
        VCPoints = 3.0;
    } else if (vcRef.value >= 1850 ) {
        VCPoints = 1.5; 
    } else {
        VCPoints = 0;
    }




    let sarPoints = 0;

    if (sarRef.value >= 26.3) {
        sarPoints = 10;
    } else if (sarRef.value >= 24.4 ) {
        sarPoints = 9.5;
    } else if (sarRef.value >= 22.4 ) {
        sarPoints = 9.0;
    } else if (sarRef.value >= 21.0 ) {
        sarPoints = 8.5;
    } else if (sarRef.value >= 19.5 ) {
        sarPoints = 8.0;
    } else if (sarRef.value >= 18.2 ) {
        sarPoints = 7.8;
    } else if (sarRef.value >= 16.9 ) {
        sarPoints = 7.6;
    } else if (sarRef.value >= 15.6 ) {
        sarPoints = 7.4;
    } else if (sarRef.value >= 14.3 ) {
        sarPoints = 7.2;
    } else if (sarRef.value >= 13.0 ) {
        sarPoints = 7.0;
    } else if (sarRef.value >= 11.7 ) {
        sarPoints = 6.8;
    } else if (sarRef.value >= 10.4 ) {
        sarPoints = 6.6;
    } else if (sarRef.value >= 9.1 ) {
        sarPoints = 6.4;
    } else if (sarRef.value >= 7.8 ) {
        sarPoints = 6.2;
    } else if (sarRef.value >= 6.5 ) {
        sarPoints = 6.0;
    } else if (sarRef.value >= 5.7 ) {
        sarPoints = 5.0;
    } else if (sarRef.value >= 4.9 ) {
        sarPoints = 4.0;
    } else if (sarRef.value >= 4.1 ) {
        sarPoints = 3.0;
    } else if (sarRef.value >= 3.3 ) {
        sarPoints = 2.0;
    } else if (sarRef.value >= 2.5 ) {
        sarPoints = 1.0;
    } else {
        sarPoints = 0;
    }



    let jumpPoints = 0;

    if (jumpRef.value >= 208) {
        jumpPoints = 10;
    } else if (jumpRef.value >= 202 ) {
        jumpPoints = 9.5;
    } else if (jumpRef.value >= 196 ) {
        jumpPoints = 9.0;
    } else if (jumpRef.value >= 189 ) {
        jumpPoints = 8.5;
    } else if (jumpRef.value >= 182 ) {
        jumpPoints = 8.0;
    } else if (jumpRef.value >= 179 ) {
        jumpPoints = 7.8;
    } else if (jumpRef.value >= 176 ) {
        jumpPoints = 7.6;
    } else if (jumpRef.value >= 173 ) {
        jumpPoints = 7.4;
    } else if (jumpRef.value >= 170 ) {
        jumpPoints = 7.2;
    } else if (jumpRef.value >= 167 ) {
        jumpPoints = 7.0;
    } else if (jumpRef.value >= 164 ) {
        jumpPoints = 6.8;
    } else if (jumpRef.value >= 161 ) {
        jumpPoints = 6.6;
    } else if (jumpRef.value >= 158 ) {
        jumpPoints = 6.4;
    } else if (jumpRef.value >= 155 ) {
        jumpPoints = 6.2;
    } else if (jumpRef.value >= 152 ) {
        jumpPoints = 6.0;
    } else if (jumpRef.value >= 147 ) {
        jumpPoints = 5.0;
    } else if (jumpRef.value >= 142 ) {
        jumpPoints = 4.0;
    } else if (jumpRef.value >= 137 ) {
        jumpPoints = 3.0;
    } else if (jumpRef.value >= 132 ) {
        jumpPoints = 2.0;
    } else if (jumpRef.value >= 127 ) {
        jumpPoints = 1.0;
    } else {
        jumpPoints = 0;
    }


    let run50Points = 0;

    if (run50Ref.value <= 7.4) {
        run50Points = 20.0;
    } else if (run50Ref.value <= 7.5) {
        run50Points = 19.0;
    } else if (run50Ref.value <= 7.6) {
        run50Points = 18.0;
    } else if (run50Ref.value <= 7.9) {
        run50Points = 17.0;
    } else if (run50Ref.value <= 8.2) {
        run50Points = 16.0;
    } else if (run50Ref.value <= 8.4) {
        run50Points = 15.6;
    } else if (run50Ref.value <= 8.6) {
        run50Points = 15.2;
    } else if (run50Ref.value <= 8.8) {
        run50Points = 14.8;
    } else if (run50Ref.value <= 9.0) {
        run50Points = 14.4;
    } else if (run50Ref.value <= 9.2) {
        run50Points = 14.0;
    } else if (run50Ref.value <= 9.4) {
        run50Points = 13.6;
    } else if (run50Ref.value <= 9.6) {
        run50Points = 13.2;
    } else if (run50Ref.value <= 9.8) {
        run50Points = 12.8;
    } else if (run50Ref.value <= 10.0) {
        run50Points = 12.4;
    } else if (run50Ref.value <= 10.2) {
        run50Points = 12.0;
    } else if (run50Ref.value <= 10.4) {
        run50Points = 10.0;
    } else if (run50Ref.value <= 10.6) {
        run50Points = 8.0;
    } else if (run50Ref.value <= 10.8) {
        run50Points = 6.0;
    } else if (run50Ref.value <= 11.0) {
        run50Points = 4.0;
    } else if (run50Ref.value <= 11.2
    ) {
        run50Points = 2.0;
    } else {
        run50Points = 0;
    }


    let run800Points = 0;
    let run800Ref = run800Min.value * 60 + run800Sec.value;

    if (run800Ref <= 146) {
        run800Points = 30.0;
    } else if (run800Ref <= 151) {
        run800Points = 29.0;
    } else if (run800Ref <= 156) {
        run800Points = 28.0;
    } else if (run800Ref <= 161) {
        run800Points = 27.0;
    } else if (run800Ref <= 166) {
        run800Points = 26.0;
    } else if (run800Ref <= 171) {
        run800Points = 25.0;
    } else if (run800Ref <= 176) {
        run800Points = 24.0;
    } else if (run800Ref <= 181) {
        run800Points = 23.0;
    } else if (run800Ref <= 186) {
        run800Points = 22.0;
    } else if (run800Ref <= 191) {
        run800Points = 21.0;
    } else if (run800Ref <= 196) {
        run800Points = 20.0;
    } else if (run800Ref <= 202) {
        run800Points = 19.0;
    } else if (run800Ref <= 208) {
        run800Points = 18.0;
    } else if (run800Ref <= 215) {
        run800Points = 17.0;
    } else if (run800Ref <= 222) {
        run800Points = 16.0;
    } else if (run800Ref <= 227) {
        run800Points = 15.6;
    } else if (run800Ref <= 232) {
        run800Points = 15.2;
    } else if (run800Ref <= 237) {
        run800Points = 14.8;
    } else if (run800Ref <= 242) {
        run800Points = 14.4;
    } else if (run800Ref <= 247) {
        run800Points = 14.0;
    } else if (run800Ref <= 252) {
        run800Points = 13.6;
    } else if (run800Ref <= 257) {
        run800Points = 13.2;
    } else if (run800Ref <= 262) {
        run800Points = 12.8;
    } else if (run800Ref <= 267) {
        run800Points = 12.4;
    } else if (run800Ref <= 272) {
        run800Points = 12.0;
    } else if (run800Ref <= 282) {
        run800Points = 10.0;
    } else if (run800Ref <= 292) {
        run800Points = 8.0;
    } else if (run800Ref <= 302) {
        run800Points = 6.0;
    } else if (run800Ref <= 312) {
        run800Points = 4.0;
    } else if (run800Ref <= 322) {
        run800Points = 2.0;
    } else {
        run800Points = 0.0;
    }

    let sitUpPoints = 0;
    if (sitUpRef.value >= 70) {
        sitUpPoints = 20.0;
    } else if (sitUpRef.value >= 69) {
        sitUpPoints = 19.0;
    } else if (sitUpRef.value >= 68) {
        sitUpPoints = 18.0;
    } else if (sitUpRef.value >= 67) {
        sitUpPoints = 17.0;
    } else if (sitUpRef.value >= 66) {
        sitUpPoints = 16.0;
    } else if (sitUpRef.value >= 65) {
        sitUpPoints = 15.0;
    } else if (sitUpRef.value >= 64) {
        sitUpPoints = 14.0;
    } else if (sitUpRef.value >= 63) {
        sitUpPoints = 13.0;
    } else if (sitUpRef.value >= 61) {
        sitUpPoints = 12.0;
    } else if (sitUpRef.value >= 59) {
        sitUpPoints = 11.0;
    } else if (sitUpRef.value >= 57) {
        sitUpPoints = 10.0;
    } else if (sitUpRef.value >= 55) {
        sitUpPoints = 9.5;
    } else if (sitUpRef.value >= 53) {
        sitUpPoints = 9.0;
    } else if (sitUpRef.value >= 50) {
        sitUpPoints = 8.5;
    } else if (sitUpRef.value >= 47) {
        sitUpPoints = 8.0;
    } else if (sitUpRef.value >= 45) {
        sitUpPoints = 7.8;
    } else if (sitUpRef.value >= 43) {
        sitUpPoints = 7.6;
    } else if (sitUpRef.value >= 41) {
        sitUpPoints = 7.4;
    } else if (sitUpRef.value >= 39) {
        sitUpPoints = 7.2;
    } else if (sitUpRef.value >= 37) {
        sitUpPoints = 7.0;
    } else if (sitUpRef.value >= 35) {
        sitUpPoints = 6.8;
    } else if (sitUpRef.value >= 33) {
        sitUpPoints = 6.6;
    } else if (sitUpRef.value >= 31) {
        sitUpPoints = 6.4;
    } else if (sitUpRef.value >= 29) {
        sitUpPoints = 6.2;
    } else if (sitUpRef.value >= 27) {
        sitUpPoints = 6.0;
    } else if (sitUpRef.value >= 25) {
        sitUpPoints = 5.0;
    } else if (sitUpRef.value >= 23) {
        sitUpPoints = 4.0;
    } else if (sitUpRef.value >= 21) {
        sitUpPoints = 3.0;
    } else if (sitUpRef.value >= 19) {
        sitUpPoints = 2.0;
    } else if (sitUpRef.value >= 17) {
        sitUpPoints = 1.0;
    } else {
        sitUpPoints = 0;
    }

    totalPoints=BMIPoints+VCPoints+sarPoints+run800Points+run50Points+sitUpPoints+jumpPoints 
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
            label="800米(min)"
            placeholder="分"
            v-model="run800Min"
            @input="handleInput"
            @blur="handleInput"
          />
          <my_input
            label="800米(s)"
            placeholder="秒"
            v-model="run800Sec"
            @input="handleInput"
            @blur="handleInput"
          />
          <my_input
            label="仰卧起坐(次)"
            placeholder="请输入仰卧起坐次数"
            v-model="sitUpRef"
            @input="handleInput"
            @blur="handleInput"
          />
</template>