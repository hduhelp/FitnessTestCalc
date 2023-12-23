<!-- <template>
    <div class="container">
      <van-icon 
        name="question-o" 
        @click="handleClick"
        style="padding-left: 5px;"
      />
      <van-dialog v-model:show="show" show-cancel-button>
        <img :src="mySrc" />
      </van-dialog>
      <div class="input">
      <van-field
        v-model="min"
        label="1000米(x分x秒)"
        placeholder="分"
        @change="emit('change')"
        @blur="updateMin"
      />
      <van-field
        v-model="sec"
        placeholder="秒"
        @change="emit('change')"
        @blur="updateSec"
      />
    </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const show = ref(false);
  const handleClick = () => {
    show.value = !show.value;
  };
  
  const props = defineProps(["label", "placeholder", "min","mySrc","sec"]);
  
  const emit = defineEmits(['update:min', 'change',"update:sec"]);
  
  const inputMin = ref(props.min);
  const inputSec = ref(props.sec);
  
  const updateMin = () => {
    emit('update:min', inputMin.value);
  };
  const updateSec = () => {
    emit('update:sec', inputSec.value);
  };
  </script>
  
  <style scoped>
  .container {
    display: flex;
    align-items: center;
  }
  .input {
    display: flex;
  }
  </style> -->
  <template>
    <div class="container">
      <van-icon name="question-o" @click="handleClick" style="padding-left: 5px;" />
      <van-dialog v-model:show="show" show-cancel-button>
        <img :src="mySrc" />
      </van-dialog>
      <div class="input">
        <van-field v-model="inputMin" label="1000米(分/秒)" placeholder="分" @change="updateMin" @blur="updateMin" />
        <van-field v-model="inputSec" placeholder="秒" @change="updateSec" @blur="updateSec" />
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const show = ref(false);
  const handleClick = () => {
    show.value = !show.value;
  };
  
  const props = defineProps(["label", "placeholder", "min", "mySrc", "sec"]);
  const emit = defineEmits(['update:min', 'update:sec']);
  
  const inputMin = ref(props.min);
  const inputSec = ref(props.sec);
  
  const updateMin = () => {
    emit('update:min', inputMin.value);
  };
  
  const updateSec = () => {
    emit('update:sec', inputSec.value);
  };
  </script>
  
  <style scoped>
  .container {
    display: flex;
    align-items: center;
  }
  .input {
    display: flex;
  }
  </style>