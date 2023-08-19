<template>
  <div>
    <nav>
      <div class="nav-bar">
        <span class="logo navLogo "
          ><Nuxt-Link to="/"
            ><img src="/images/spendControlLogo.svg" alt="KenFront logo" /></Nuxt-Link
        ></span>
        <!-- <i class='bx bx-menu sidebarOpen' ></i> -->

        <v-app-bar-nav-icon
          class="d-md-none d-block text-white"
          variant="text"
          @click.stop="openDrawer"
        ></v-app-bar-nav-icon>
        <div class="menu">
          <div class="logo-toggle">
            <span class="logo"
              ><NuxtLink to="/"><img src="/images/spendControlLogo.svg" alt="KenFront logo" /></NuxtLink
            ></span>
            <!-- <i class='bx bx-x siderbarClose'></i>  -->
          </div>

          <ul class="nav-links">
            <li>
                  <v-btn
                    variant="text"
                    rounded
                    class="services text-white"
                    ><span style="font-weight: 300;">About</span></v-btn>

                <!-- <v-list>
                  <v-list-item v-for="(item, index) in services" :key="index">
                    <NuxtLink
                      style="
                        cursor: pointer;
                        text-decoration: none;
                        color: rgb(71, 70, 70);
                      "
                      :to="item.to"
                    >
                      <v-list-item-title>{{ item.service }}</v-list-item-title>
                    </NuxtLink>
                  </v-list-item>
                </v-list> -->
            </li>
            <li>
                  <v-btn
                    variant="text"
                    rounded
                    class="products text-white"
                    to="casestudies"
                    ><span style="font-weight: 300;">Case Studies</span>
                  </v-btn>

                <!-- <v-list>
                  <v-list-item v-for="(item, index) in products" :key="index">
                    <NuxtLink
                      style="
                        cursor: pointer;
                        text-decoration: none;
                        color: rgb(71, 70, 70);
                      "
                      :to="item.to"
                    >
                      <v-list-item-title>{{ item.product }}</v-list-item-title>
                    </NuxtLink>
                  </v-list-item>
                </v-list> -->
            </li>
            <li>
              <v-btn
                class="products text-white"
                variant="text"
                rounded
                to="blogs"
                ><span style="font-weight: 300;">Blogs</span></v-btn
              >
            </li>
            <li>
              <v-btn
                variant="outlined"
                rounded
                class="contact-us text-white"
                ><span style="font-weight: 300;">Contact</span></v-btn
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>

<script setup>
let drawer = ref(false);
let group = ref(null);
let services = ref([
  {
    service: "Data Science as a Service",
    to: "/",
  },
  { service: "IDEA", to: "/" },
  { service: "Incorta", to: "/" },
  { service: "Enterprises Analytics", to: "/" },
]);
let products = ref([
  {
    product: "Carrom Live",
    to: "/",
  },
  {
    product: "Spend Control",
    to: "/",
  },
]);
let items = ref([
  {
    title: "Services",
  },
  {
    title: "Products",
  },
  {
    title: "About Us",
  },
  {
    title: "Contact Us",
  },
]);
const emit = defineEmits(["customEvent"]);

let openDrawer = async () => {
  drawer.value = true;
  emit("customEvent", drawer.value);
};
</script>
<style scoped>
nav {
  position: fixed;
  top: 0;
  left: 0;
  border-radius: 10vw;
  background: #0f0f0f4a;
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
  backdrop-filter: blur(3px);
  -webkit-backdrop-filter: blur(3px);
  height: 10%;
  margin: 2% 3%;
  width: 94%;
  z-index: 100;
}
nav .nav-bar {
  position: relative;
  height: 90%;
  width: 90%;
  margin: 0 auto;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
/* v-navigation-drawer{
        top: 20;
    } */
.sidebarOpen {
  color: white;
  font-size: 2rem;
  padding: 5px;
  cursor: pointer;
  display: none;
}

nav .nav-bar .logo v-btn {
  font-weight: 500;
  color: white;
  text-decoration: none;
}
.logo img {
  height: 8vh;
  padding-top: 8%;
}

.menu .logo-toggle {
  display: none;
}

.nav-bar .nav-links {
  display: flex;
  align-items: center;
}

.nav-bar .nav-links li {
  color: white;
  margin: 0 10px;
  list-style: none;
  overflow: hidden;
}

.nav-links li v-btn {
  font-family: "Montserrat", sans-serif;
  font-weight: 200;
  position: relative;
  font-size: 17px;
  font-weight: 400;
  color: white;
  text-decoration: none;
  padding: 10px;
}

.nav-links li v-btn::before {
  content: "";
  position: absolute;
  left: 50%;
  bottom: 0;
  transform: translateX(-50%);
  height: 6px;
  width: 6px;
  border-radius: 50%;
  opacity: 0;
  transition: all 0.3s ease;
}

.nav-links li:hover v-btn::before {
  opacity: 1;
}

@media (max-width: 900px) {
  nav .nav-bar .sidebarOpen {
    display: block;
  }
  .imgl,
  .imgr,
  .imgtl {
    display: none !important;
  }
  .menu {
    position: fixed;
    height: 100%;
    width: 220px;
    right: -100%;
    top: 0;
    background-color: #4129f4;
    z-index: 100;
    transition: all 0.4s ease;
    overflow: scroll !important;
  }

  nav.active .menu {
    right: -0%;
  }

  nav.active .nav-bar .navLogo v-btn {
    opacity: 0;
    transition: all 0.3s ease;
  }

  .menu .logo-toggle {
    display: block;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-around;
  }

  .logo-toggle .siderbarClose {
    font-size: 24px;
    cursor: pointer;
  }
  .nav-links i {
    display: none;
  }
  .nav-bar .nav-links {
    flex-direction: column;
    padding-top: 30px;
  }
  .nav-links li v-btn {
    display: block;
    margin-top: 20px;
  }
}

@media only screen and (max-width: 1599px) and (min-width: 1366px) {
  .nav-bar .nav-links v-btn {
    font-size: 1rem;
  }
}
@media only screen and (max-width: 1365px) and (min-width: 1024px) {
  .nav-bar .nav-links v-btn {
    font-size: 0.8rem;
  }
}
</style>
