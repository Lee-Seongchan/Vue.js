<script>
export default {
  name: "EmitComponent1",
  props: ["name", "age"],
  data() {
    return {
      myname: this.name,
      myage: this.age,
    };
  },
  methods: {
    btnEmit: function () {
      //alert("click!");

      //상위 컴포넌트로 발생
      const emitData = {
        name: this.myname,
        age: this.myage,
      };

      // 상위 컴포넌트로 myEmit 이벤트 발생
      this.$emit("myEmit", emitData); //myEmit이라는 이벤트 emitData 는 제이슨 데이터
    },
  },
};
</script>

<template>
  <p>
    이름:<input type="text" v-model="myname" /><br />
    나이:<input type="text" v-model="myage" /><br />
  </p>
  <button @click="btnEmit">전달</button>
</template>

<style scoped></style>
