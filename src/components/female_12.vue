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

    if (vcRef.value >= 3400) {
        VCPoints = 15.0;
    } else if (vcRef.value >= 3350 ) {
        VCPoints = 14.25;
    } else if (vcRef.value >= 3300 ) {
        VCPoints = 13.5;
    } else if (vcRef.value >= 3150 ) {
        VCPoints = 12.75;
    } else if (vcRef.value >= 3000 ) {
        VCPoints = 12.0;
    } else if (vcRef.value >= 2900 ) {
        VCPoints = 11.7;
    } else if (vcRef.value >= 2800 ) {
        VCPoints = 11.4;
    } else if (vcRef.value >= 2700 ) {
        VCPoints = 11.1;
    } else if (vcRef.value >= 2600 ) {
        VCPoints = 10.8;
    } else if (vcRef.value >= 2500 ) {
        VCPoints = 10.5;
    } else if (vcRef.value >= 2400 ) {
        VCPoints = 10.2;
    } else if (vcRef.value >= 2300 ) {
        VCPoints = 9.9;
    } else if (vcRef.value >= 2200 ) {
        VCPoints = 9.6;
    } else if (vcRef.value >= 2100 ) {
        VCPoints = 9.3;
    } else if (vcRef.value >= 2000 ) {
        VCPoints = 9.0;
    } else if (vcRef.value >= 1960 ) {
        VCPoints = 7.5;
    } else if (vcRef.value >= 1920 ) {
        VCPoints = 6.0;
    } else if (vcRef.value >= 1880 ) {
        VCPoints = 4.5;
    } else if (vcRef.value >= 1840 ) {
        VCPoints = 3.0;
    } else if (vcRef.value >= 1800 ) {
        VCPoints = 1.5; 
    } else {
        VCPoints = 0;
    }




    let sarPoints = 0;

    if (sarRef.value >= 25.8) {
        sarPoints = 10;
    } else if (sarRef.value >= 24.0 ) {
        sarPoints = 9.5;
    } else if (sarRef.value >= 22.2 ) {
        sarPoints = 9.0;
    } else if (sarRef.value >= 20.6 ) {
        sarPoints = 8.5;
    } else if (sarRef.value >= 19.0 ) {
        sarPoints = 8.0;
    } else if (sarRef.value >= 17.7 ) {
        sarPoints = 7.8;
    } else if (sarRef.value >= 16.4 ) {
        sarPoints = 7.6;
    } else if (sarRef.value >= 15.1 ) {
        sarPoints = 7.4;
    } else if (sarRef.value >= 13.8 ) {
        sarPoints = 7.2;
    } else if (sarRef.value >= 12.5 ) {
        sarPoints = 7.0;
    } else if (sarRef.value >= 11.2 ) {
        sarPoints = 6.8;
    } else if (sarRef.value >= 9.9 ) {
        sarPoints = 6.6;
    } else if (sarRef.value >= 8.6 ) {
        sarPoints = 6.4;
    } else if (sarRef.value >= 7.3 ) {
        sarPoints = 6.2;
    } else if (sarRef.value >= 6.0 ) {
        sarPoints = 6.0;
    } else if (sarRef.value >= 5.2 ) {
        sarPoints = 5.0;
    } else if (sarRef.value >= 4.4 ) {
        sarPoints = 4.0;
    } else if (sarRef.value >= 3.6 ) {
        sarPoints = 3.0;
    } else if (sarRef.value >= 2.8 ) {
        sarPoints = 2.0;
    } else if (sarRef.value >= 2.0 ) {
        sarPoints = 1.0;
    } else {
        sarPoints = 0;
    }



    let jumpPoints = 0;

    if (jumpRef.value >= 207) {
        jumpPoints = 10;
    } else if (jumpRef.value >= 201 ) {
        jumpPoints = 9.5;
    } else if (jumpRef.value >= 195 ) {
        jumpPoints = 9.0;
    } else if (jumpRef.value >= 188 ) {
        jumpPoints = 8.5;
    } else if (jumpRef.value >= 181 ) {
        jumpPoints = 8.0;
    } else if (jumpRef.value >= 178 ) {
        jumpPoints = 7.8;
    } else if (jumpRef.value >= 175 ) {
        jumpPoints = 7.6;
    } else if (jumpRef.value >= 172 ) {
        jumpPoints = 7.4;
    } else if (jumpRef.value >= 169 ) {
        jumpPoints = 7.2;
    } else if (jumpRef.value >= 166 ) {
        jumpPoints = 7.0;
    } else if (jumpRef.value >= 163 ) {
        jumpPoints = 6.8;
    } else if (jumpRef.value >= 160 ) {
        jumpPoints = 6.6;
    } else if (jumpRef.value >= 157 ) {
        jumpPoints = 6.4;
    } else if (jumpRef.value >= 154 ) {
        jumpPoints = 6.2;
    } else if (jumpRef.value >= 151 ) {
        jumpPoints = 6.0;
    } else if (jumpRef.value >= 146 ) {
        jumpPoints = 5.0;
    } else if (jumpRef.value >= 141 ) {
        jumpPoints = 4.0;
    } else if (jumpRef.value >= 136 ) {
        jumpPoints = 3.0;
    } else if (jumpRef.value >= 131 ) {
        jumpPoints = 2.0;
    } else if (jumpRef.value >= 126 ) {
        jumpPoints = 1.0;
    } else {
        jumpPoints = 0;
    }


    let run50Points = 0;

    if (run50Ref.value <= 7.5) {
        run50Points = 20.0;
    } else if (run50Ref.value <= 7.6) {
        run50Points = 19.0;
    } else if (run50Ref.value <= 7.7) {
        run50Points = 18.0;
    } else if (run50Ref.value <= 8.0) {
        run50Points = 17.0;
    } else if (run50Ref.value <= 8.3) {
        run50Points = 16.0;
    } else if (run50Ref.value <= 8.5) {
        run50Points = 15.6;
    } else if (run50Ref.value <= 8.7) {
        run50Points = 15.2;
    } else if (run50Ref.value <= 8.9) {
        run50Points = 14.8;
    } else if (run50Ref.value <= 9.1) {
        run50Points = 14.4;
    } else if (run50Ref.value <= 9.3) {
        run50Points = 14.0;
    } else if (run50Ref.value <= 9.5) {
        run50Points = 13.6;
    } else if (run50Ref.value <= 9.7) {
        run50Points = 13.2;
    } else if (run50Ref.value <= 9.9) {
        run50Points = 12.8;
    } else if (run50Ref.value <= 10.1) {
        run50Points = 12.4;
    } else if (run50Ref.value <= 10.3) {
        run50Points = 12.0;
    } else if (run50Ref.value <= 10.5) {
        run50Points = 10.0;
    } else if (run50Ref.value <= 10.7 ) {
        run50Points = 8.0;
    } else if (run50Ref.value <= 10.9) {
        run50Points = 6.0;
    } else if (run50Ref.value <= 11.1) {
        run50Points = 4.0;
    } else if (run50Ref.value <= 11.3) {
        run50Points = 2.0;
    } else {
        run50Points = 0;
    }


    let run800Points = 0;
    let run800Ref = run800Min.value * 60 + run800Sec.value;

    if (run800Ref <= 148) {
    run800Points = 30.0;
    } else if (run800Ref <= 153) {
        run800Points = 29.0;
    } else if (run800Ref <= 158) {
        run800Points = 28.0;
    } else if (run800Ref <= 163) {
        run800Points = 27.0;
    } else if (run800Ref <= 168) {
        run800Points = 26.0;
    } else if (run800Ref <= 173) {
        run800Points = 25.0;
    } else if (run800Ref <= 178) {
        run800Points = 24.0;
    } else if (run800Ref <= 183) {
        run800Points = 23.0;
    } else if (run800Ref <= 188) {
        run800Points = 22.0;
    } else if (run800Ref <= 193) {
        run800Points = 21.0;
    } else if (run800Ref <= 198) {
        run800Points = 20.0;
    } else if (run800Ref <= 204) {
        run800Points = 19.0;
    } else if (run800Ref <= 210) {
        run800Points = 18.0;
    } else if (run800Ref <= 217) {
        run800Points = 17.0;
    } else if (run800Ref <= 224) {
        run800Points = 16.0;
    } else if (run800Ref <= 229) {
        run800Points = 15.6;
    } else if (run800Ref <= 234) {
        run800Points = 15.2;
    } else if (run800Ref <= 239) {
        run800Points = 14.8;
    } else if (run800Ref <= 244) {
        run800Points = 14.4;
    } else if (run800Ref <= 249) {
        run800Points = 14.0;
    } else if (run800Ref <= 254) {
        run800Points = 13.6;
    } else if (run800Ref <= 259) {
        run800Points = 13.2;
    } else if (run800Ref <= 264) {
        run800Points = 12.8;
    } else if (run800Ref <= 269) {
        run800Points = 12.4;
    } else if (run800Ref <= 274) {
        run800Points = 12.0;
    } else if (run800Ref <= 284) {
        run800Points = 10.0;
    } else if (run800Ref <= 294) {
        run800Points = 8.0;
    } else if (run800Ref <= 304) {
        run800Points = 6.0;
    } else if (run800Ref <= 314) {
        run800Points = 4.0;
    } else if (run800Ref <= 324) {
        run800Points = 2.0;
    } else {
        run800Points = 0.0;
    }

    let sitUpPoints = 0;
    if (sitUpRef.value >= 69) {
        sitUpPoints = 20.0;
    } else if (sitUpRef.value >= 68) {
        sitUpPoints = 19.0;
    } else if (sitUpRef.value >= 67) {
        sitUpPoints = 18.0;
    } else if (sitUpRef.value >= 66) {
        sitUpPoints = 17.0;
    } else if (sitUpRef.value >= 65) {
        sitUpPoints = 16.0;
    } else if (sitUpRef.value >= 64) {
        sitUpPoints = 15.0;
    } else if (sitUpRef.value >= 63) {
        sitUpPoints = 14.0;
    } else if (sitUpRef.value >= 62) {
        sitUpPoints = 13.0;
    } else if (sitUpRef.value >= 60) {
        sitUpPoints = 12.0;
    } else if (sitUpRef.value >= 58) {
        sitUpPoints = 11.0;
    } else if (sitUpRef.value >= 56) {
        sitUpPoints = 10.0;
    } else if (sitUpRef.value >= 54) {
        sitUpPoints = 9.5;
    } else if (sitUpRef.value >= 52) {
        sitUpPoints = 9.0;
    } else if (sitUpRef.value >= 49) {
        sitUpPoints = 8.5;
    } else if (sitUpRef.value >= 46) {
        sitUpPoints = 8.0;
    } else if (sitUpRef.value >= 44) {
        sitUpPoints = 7.8;
    } else if (sitUpRef.value >= 42) {
        sitUpPoints = 7.6;
    } else if (sitUpRef.value >= 40) {
        sitUpPoints = 7.4;
    } else if (sitUpRef.value >= 38) {
        sitUpPoints = 7.2;
    } else if (sitUpRef.value >= 36) {
        sitUpPoints = 7.0;
    } else if (sitUpRef.value >= 34) {
        sitUpPoints = 6.8;
    } else if (sitUpRef.value >= 32) {
        sitUpPoints = 6.6;
    } else if (sitUpRef.value >= 30) {
        sitUpPoints = 6.4;
    } else if (sitUpRef.value >= 28) {
        sitUpPoints = 6.2;
    } else if (sitUpRef.value >= 26) {
        sitUpPoints = 6.0;
    } else if (sitUpRef.value >= 24) {
        sitUpPoints = 5.0;
    } else if (sitUpRef.value >= 22) {
        sitUpPoints = 4.0;
    } else if (sitUpRef.value >= 20) {
        sitUpPoints = 3.0;
    } else if (sitUpRef.value >= 18) {
        sitUpPoints = 2.0;
    } else if (sitUpRef.value >= 16) {
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