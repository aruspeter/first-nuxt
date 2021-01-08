<template>
    <div class="cursor" id="mews">
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
        <div class="cursor-center" ></div>
    </div>
</template>

<script>
    export default {
    mounted(){
      const menu =  Array.from(document.getElementsByTagName('a'));
      const mews = document.getElementById('mews');
      const mewsCenters = Array.from(document.querySelectorAll('.cursor-center'));

      function randomNumber(min, max){
          return Math.random() * (max - min) + min;
      }

      document.addEventListener('mousemove', (e) => {
          mews.setAttribute("style", `top: ${e.pageY - 10}px; left: ${e.pageX - 10}px;`);
          for (let i = 0; i < mewsCenters.length; i++){
            mewsCenters[i].setAttribute("style", `top: ${e.pageY/(i + 1) - randomNumber(0-(i + 1)*50, (i + 1)*50)}px; left: ${e.pageX/(i + 1) - randomNumber(0-(i + 1)*50, (i + 1)*50)}px;`);
          }
      })
      menu.forEach(item => {
        item.addEventListener("mouseover", () => {
          mews.classList.add("blue");
          mewsCenters.forEach(guy => {
            guy.classList.add('steady');
          })
        })
        item.addEventListener("mouseout", () =>{
          mews.classList.remove("blue");
          mewsCenters.forEach(guy => {
            guy.classList.remove('steady');
          })
        })
      })
  }
}
</script>