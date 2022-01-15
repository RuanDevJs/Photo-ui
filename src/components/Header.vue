<template>
  <transition leave-to-class="fadeOut">
    <header :class="['header', { active: active, disable: disable }]">
      <ul class="menu">
        <li class="menu-item">
          <a href="#" @click.prevent="handleClick('Home')">Home</a>
        </li>
        <li class="menu-item">
          <a href="#" @click.prevent="handleClick('Login')">Login</a>
        </li>
      </ul>
    </header>
  </transition>
</template>

<script>
export default {
  name: "Header",
  props: ["propActiveComponent"],
  data() {
    return {
      active: false,
      disable: true,
      activeComponent: this.propActiveComponent,
    };
  },
  methods: {
    handleMenu({ key }) {
      if (key === "Escape") {
        this.active = !this.active;
        this.disable = !this.disable;
      }
    },
    handleClick(component) {
      this.$emit("update:activeComponent", component);
      this.active = false;
    },
  },
  mounted() {
    window.addEventListener("keyup", this.handleMenu);
  },
};
</script>

<style scoped>
.header {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;

  height: 0px;
  width: 0px;
  display: none;
  flex-flow: column wrap;
  align-items: center;
  justify-content: center;

  background: #82e;
  z-index: 1000;
}

.header.active {
  display: flex;
  animation: FadeIn 0.5s forwards;
  transition: 0.5s ease-in-out;
}

.menu-item {
  padding: 12px;
  margin: 20px;
}

.menu-item a {
  display: block;
  text-decoration: none;

  font-size: 18px;
  font-weight: 500;
  color: #f2f2f2;

  text-align: left;
}

@keyframes FadeIn {
  from {
    display: none;
    width: 0;
    height: 0;
  }
  to {
    display: none;
    width: 100%;
    height: 100vh;
  }
}

@keyframes FadeOut {
  from {
    display: flex;
    width: 100%;
    height: 100vh;
  }
  to {
    display: none;
    width: 0px;
    height: 0px;
  }
}
</style>