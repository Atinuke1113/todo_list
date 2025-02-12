<template>
  <div class="w-full">
    <HomeHero></HomeHero>
    
    <div class="flex  justify-center items-center ">
      <img class="xs:w-[80%] animate__animated animate__bounceInUp pb-8 md:w-[50%] md:-mt-[200px] lg:-mt-[200px] 2xl:-mt-[250px] lg:w-[50%] 2xl:w-[40%]  xs:-mt-[120px]" src="@/assets/img/bg.png" alt="" />
    </div>
    <HomeInfo></HomeInfo>
    <HomeInfo2></HomeInfo2>
    <HomeSector></HomeSector>
    <HomeAlumni>

    </HomeAlumni>
   
  </div>
</template>

<script>
export default {
  setup() {
    definePageMeta({
      layout: "home",
    });
  },
  data: () => ({}),
  mounted() {},
};
</script>

<style></style>
