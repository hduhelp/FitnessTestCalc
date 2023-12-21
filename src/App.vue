<script setup>
    import {ref} from "vue"
    import male_12 from "./components/male_12.vue"
    import male_34 from "./components/male_34.vue"
    import female_12 from "./components/female_12.vue"
    import female_34 from "./components/female_34.vue"
    let gender=ref("")
    let grade=ref("")
</script>

<template>
    <van-nav-bar
      title="体测计算器"
      left-text="返回"
      left-arrow
    />
    <van-cell-group inset style="margin-top: 20px;">
      <van-cell title="请选择性别">
        <van-radio-group v-model="gender" direction="horizontal">
            <van-radio name="male">男</van-radio>
            <van-radio name="female">女</van-radio>
        </van-radio-group>
      </van-cell>
      <van-cell title="请选择年级">
        <van-radio-group v-model="grade" direction="horizontal">
            <van-radio name="grade12">大一/二</van-radio>
            <van-radio name="grade34">大三/四</van-radio>
        </van-radio-group>
      </van-cell>
      <male_12
        v-if="gender==='male'&&grade==='grade12'"
      />
      <male_34
        v-if="gender==='male'&&grade==='grade34'"
      />
      <female_12
        v-if="gender==='female'&&grade==='grade12'"
      />
      <female_34
        v-if="gender==='female'&&grade==='grade34'"
      />
        
    </van-cell-group>

</template>

<style>
    body{
      background-color: #e9e9eb;
    }
    .head{
      position: fixed;
    }
</style>

<!--
     ui优化，输入格子加一点分割线，对齐和按钮位置/单位位置都优化一下，在每个项目名称左侧设置一个问号小图标，弹出有每一项标准的模态框，顶部栏优化！！，进度条优化，弹出一个总的得分标准和小tips之类的，在背景加上杭助的水印
    -->
    
