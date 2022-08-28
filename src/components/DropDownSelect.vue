<template>
  <div class="flex justify-end items-center mx-[20px]">
    <button
      @click="handleShowAllCheck"
      class="
        h-full
        text-[14px] text-[#ffffff]
        bg-[#97d077]
        p-[5px]
        items-center
        rounded
      "
    >
      reservation_calendar.text_button
    </button>
  </div>
  <div class="w-full flex justify-center mt-[12px]" >
    <check-plan-in-week
      :isCheck="ShowAllCheckRegister"
      @ShowAllCheckRegister="handleBackAllCheck"
      :focus="1"
    />
    <check-plan-in-money
      :isCheck="ShowAllCheckRegister"
      @ShowAllCheckRegister="handleBackAllCheck"
       :focus="2"
    />
  </div>
  <div
    v-if="ShowAllCheckRegister"
    class="w-full m-auto border-t-2 border-solid border-[#626262] my-3"
  >
    <div
      class="
        py-[10px]
        px-[30px]
        text-[20px]
        mt-[5px]
        arounded
        text-[#ffffff]
        items-center
        text-center
        bg-[#31B11D]
        cursor-pointer
      "
    >
      reservation_calendar.no_inform
    </div>
    <div
      class="
        py-[10px]
        px-[30px]
        text-[20px]
        mt-[5px]
        arounded
        text-[#ffffff]
        items-center
        text-center
        bg-[#f16a99]
        cursor-pointer
      "
    >
      reservation_calendar.set_unavailable
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import CheckPlanInWeek from "./CheckPlanInWeek.vue";
import CheckPlanInMoney from "./CheckPlanInMoney.vue";
export default {
  components: { CheckPlanInWeek, CheckPlanInMoney },
  name: "DropDownSelect",
  setup() {
    const ShowAllCheckRegister = ref(false);
    const isCheck = ref(false);
    const focus = ref(Number);
    const handleShowAllCheck = () => {
      ShowAllCheckRegister.value = !ShowAllCheckRegister.value;
    };
    const handleBackAllCheck = () => {
      ShowAllCheckRegister.value = false;
    };
    return {
      ShowAllCheckRegister,
      isCheck,
      focus,
      handleShowAllCheck,
      handleBackAllCheck,
    };
  },
};
</script>

<style>
</style>
