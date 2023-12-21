<!-- <template>
  <van-icon 
    name="question-o" 
    @click="handleClick"
  />
  <van-dialog v-model:show="show" show-cancel-button>
    <img src="../assets/HDUhelp2.jpg" />
  </van-dialog>
  <van-field
    v-model="inputValue"
    :label="label"
    :placeholder="placeholder"
    @change="emit('change')"
    @blur="updateInputValue"
  />
</template>

<script setup>
import { ref, defineProps, defineEmits } from 'vue';

const show = ref(false);
const handleClick = () => {
  show.value = !show.value;
};

const props = defineProps(["label", "placeholder", "modelValue"]);

const emit = defineEmits(['update:modelValue', 'change']);

const inputValue = ref(props.modelValue);

const updateInputValue = () => {
  emit('update:modelValue', inputValue.value);
};
</script> -->


<template>
  <div class="container">
    <van-icon 
      name="question-o" 
      @click="handleClick"
      style="padding-left: 5px;"
    />
    <van-dialog v-model:show="show" show-cancel-button>
      <img :src="mySrc" />
    </van-dialog>
    <van-field
      v-model="inputValue"
      :label="label"
      :placeholder="placeholder"
      @change="emit('change')"
      @blur="updateInputValue"
    />
  </div>
</template>

<script setup>
import { ref } from 'vue';

const show = ref(false);
const handleClick = () => {
  show.value = !show.value;
};

const props = defineProps(["label", "placeholder", "modelValue","mySrc"]);

const emit = defineEmits(['update:modelValue', 'change']);

const inputValue = ref(props.modelValue);

const updateInputValue = () => {
  emit('update:modelValue', inputValue.value);
};
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
}
</style>

