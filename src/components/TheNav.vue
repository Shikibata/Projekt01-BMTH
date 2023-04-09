<template>
  <button class="burger" @click="toggleMenu" :class="{ button_active: isOpen }">
      <span class="burger_icon"></span>
  </button>
  <aside class="menu" :class="{ menu_active: isOpen }">
    <div class="menu_inner">
      <div class="menu_header">
        <div class="menu_name">
          <h1>BRING ME THE HORIZON</h1>
        </div>
        <button class="burger" @click="toggleMenu" :class="{ button_active: isOpen }">
          <span class="burger_icon"></span>
      </button>
    </div>
    </div>
  </aside>
</template>

<script setup>
import { ref } from "vue";

const isOpen = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};

</script>

<style scoped>
.burger {
  position: fixed;
  top: 40px;
  right: 30px;
  transform: rotate(90deg);
  z-index: 998;
  cursor: pointer;
  border: 0;
  background: transparent;
  padding: 0;
  margin: 0;

}

.burger_icon {
  position: relative;
  margin-top: 8px;
  margin-bottom: 8px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.burger_icon, .burger_icon::before, .burger_icon::after {
  padding-left: 4px;
  display: block;
  width: 30px;
  height: 3px;
  background-color: #5800e3;
  outline: 1px solid transparent;
  -webkit-transition-property: background-color,-webkit-transform;
  -moz-transition-property: background-color,-moz-transform;
  -o-transition-property: background-color,-o-transform;
  transition-property: background-color,transform;
  -webkit-transition-duration: .3s;
  -moz-transition-duration: .3s;
  -o-transition-duration: .3s;
  transition-duration: .3s;
}

.burger_icon::before, .burger_icon::after {
  content: "";
  position: absolute;
}

.burger_icon::before {
  top: -10px;
}

.burger_icon::after {
  top: 10px;
}

.menu_active {
  display: block!important;
}

.menu {
  height: calc(1vh *100);
  width: 100%;
  border: var(--borderBody) solid #fafafa;
  padding-top: var(--borderBody);
  position: fixed;
  background-color: #fafafa;
  max-height: 100%;
  display: none;
  top: 0;
  left: 0;
  z-index: 1000;
  overflow: hidden;
}

.button_active .burger_icon::before {
  -webkit-transform: translateY(10px) rotate(45deg);
  -moz-transform: translateY(10px) rotate(45deg);
  -ms-transform: translateY(10px) rotate(45deg);
  -o-transform: translateY(10px) rotate(45deg);
  transform: translateY(10px) rotate(45deg);
}

.button_active .burger_icon::after {
  -webkit-transform: translateY(-10px) rotate(-45deg);
  -moz-transform: translateY(-10px) rotate(-45deg);
  -ms-transform: translateY(-10px) rotate(-45deg);
  -o-transform: translateY(-10px) rotate(-45deg);
  transform: translateY(-10px) rotate(-45deg);
}

.button_active .burger_icon {
  background-color: transparent;
}

.button_active .burger_icon::before, .button_active .burger_icon::after {
  background-color: black;
}

.menu_header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
}

.menu_name h1 {
  font-family: "Shirens";
  font-size: clamp(0.5rem, 4vw, 3rem);
}

.menu_header .burger {
  transform: rotate(25deg);
}
</style>