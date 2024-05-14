<template>
  <div class="corFundo">
    <div class="header">
      <input type="checkbox" class="openSidebarMenu" id="openSidebarMenu" />
      <label for="openSidebarMenu" class="sidebarIconToggle">
        <div class="spinner diagonal part-1"></div>
        <div class="spinner horizontal"></div>
        <div class="spinner diagonal part-2"></div>
      </label>
      <div id="sidebarMenu">
        <ul class="sidebarMenuInner">
          <li>Kelvis dev <span>Menu</span></li>
          <li><a href="#">Home</a></li>
          <li><a href="#">Costumer</a></li>
          <li><a href="#">Estatisticas</a></li>
          <li><a href="#">Outros</a></li>
        </ul>
      </div>
    </div>
    <div class="row mt-4 m-0 justify-content-center">
      <Cards :titulo="'Saldo'"/>
      <Cards :titulo="'Despesa'"/>
      <Cards :titulo="'Outros'"/>
      <Boxcenter :titulo="'Boxcenter'" />
    </div>
   
  </div>
  
</template>

<script>
import Cards from "../components/Cards.vue";
import Boxcenter from '@/components/Boxcenter.vue';


export default {
  name: "home",
  components: {
    Cards,
    Boxcenter,
  },
  data(){
   return{
     isSidebarOpen: false,
   };
  },

};

</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Varela+Round");


.corFundo {
  background-color: #110932;

}

.header {
  display: block;
  margin: 0 auto;
  width: 100%;
  max-width: 100%;
  box-shadow: none;
  background-color: #201b2c;
  position: relative;
  height: 60px !important;
  overflow: hidden;
  z-index: 10;
}

.main {
  margin: 0 auto;
  display: block;
  height: 100%;
  margin-top: 60px;
}

.mainInner {
  display: table;
  height: 100%;
  width: 100%;
  text-align: center;
}

.mainInner div {
  display: table-cell;
  vertical-align: middle;
  font-size: 3em;
  font-weight: bold;
  letter-spacing: 1.25px;
}

#sidebarMenu {
  height: 100%;
  position: fixed;
  left: 0;
  width: 250px;
  margin-top: 60px;
  transform: translateX(-250px);
  transition: transform 250ms ease-in-out;
  background: linear-gradient(180deg,  #00000056 50%, #514869 100%);
}

.sidebarMenuInner {
  margin: 0;
  padding: 0;
  border-top: 1px solid rgba(255, 255, 255, 0.11);
}

.sidebarMenuInner li {
  list-style: none;
  color: #77ffc0;
  text-transform: uppercase;
  font-weight: bold;
  padding: 20px;
  cursor: pointer;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.sidebarMenuInner li span {
  display: block;
  font-size: 14px;
  color: rgba(255, 255, 255, 0.5);
}

.sidebarMenuInner li a {
  color: #77ffc0;
  text-transform: uppercase;
  font-weight: bold;
  cursor: pointer;
  text-decoration: none;
}



input[type="checkbox"]:checked ~ #sidebarMenu {
  transform: translateX(0);
}

input[type="checkbox"] {
  transition: all 0.3s;
  box-sizing: border-box;
  display: none;
}

.sidebarIconToggle {
  transition: all 0.3s;
  box-sizing: border-box;
  cursor: pointer;
  position: absolute;
  z-index: 99;
  height: 100%;
  width: 100%;
  top: 22px;
  left: 15px;
  height: 22px;
  width: 22px;
}

.spinner {
  transition: all 0.3s;
  box-sizing: border-box;
  position: relative;
  height: 3px;
  width: 100%;
  background-color: #fff;
  margin: 2px 0;
}
</style>
