<!--******************
  TEMPLATE SECTION
*******************-->
<template>
  <the-header title="RememberMe"></the-header>
  <the-resources></the-resources>
</template>
<!--********************
  END TEMPLATE SECTION
*********************-->

<!--******************
  SCRIPT
*******************-->
<script>

  //Import
  import TheHeader from "./components/layouts/TheHeader";
  import TheResources from "./components/learning-resources/TheResources";

  export default {

    //Register Component
    components:{
      TheHeader,
      TheResources
    },
  }
</script>
<!--******************
  EDN SCRIPT
*******************-->


<!--******************
  STYLES
*******************-->
<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto+Condensed&display=swap');

  body{
    font-family: "Roboto Condensed";
    margin: 0 auto;
  }
</style>

<!--******************
  END STYLES
*******************-->