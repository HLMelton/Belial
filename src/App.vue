<script setup>

// Need to reformat to fit into Vue Framework
const toggleNav = () => {
  document.body.dataset.nav = document.body.dataset.nav === "true" ? "false" : "true";
}


</script>

<template>
  <nav>
    <div id="nav-links">
      <a class="nav-link" href="#">
        <h2 class="nav-link-label rubik-font">Home</h2>
        <img class="nav-link-image"
          src="https://images.unsplash.com/photo-1666091863721-54331a5db52d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=987&q=80" />
      </a>
      <a class="nav-link" href="#">
        <h2 class="nav-link-label rubik-font">Work</h2>
        <img class="nav-link-image"
          src="https://images.unsplash.com/photo-1666055642230-1595470b98fd?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=995&q=80" />
      </a>
      <a class="nav-link" href="#">
        <h2 class="nav-link-label rubik-font">About</h2>
        <img class="nav-link-image"
          src="https://images.unsplash.com/photo-1666005487638-61f45819c975?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=987&q=80" />
      </a>
      <a class="nav-link" href="#">
        <h2 class="nav-link-label rubik-font">Contact</h2>
        <img class="nav-link-image"
          src="https://images.unsplash.com/photo-1665910407771-bc84ad45676b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=776&q=80" />
      </a>
      <a class="nav-link" href="#">
        <h2 class="nav-link-label rubik-font">Join Us</h2>
        <img class="nav-link-image"
          src="https://images.unsplash.com/photo-1553356084-58ef4a67b2a7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=987&q=80" />
      </a>
    </div>
  </nav>

  <button id="nav-toggle" type="button" onclick="toggleNav()">
    <i class="open fa-light fa-bars-staggered"></i>
    <i class="close fa-light fa-xmark-large"></i>
  </button>
</template>

<style>
body {
  height: 100vh;
  width: 100vw;
  margin: 0px;
  background-color: black;
}

.rubik-font {
  font-family: "Rubik", sans-serif;
}

main {
  background-image: url("https://images.unsplash.com/photo-1666032234128-abc3e45bd1dc?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2670&q=80");
  background-position: center 0%;
  background-size: cover;
  height: 100vh;
  width: 100vw;
  position: relative;
  z-index: 2;
  transition: transform 500ms cubic-bezier(.13, .53, .38, .97);
}

body[data-nav="true"]>main {
  transform: translateY(-50%);
}

nav {
  height: 50vh;
  width: 100%;
  position: absolute;
  left: 0px;
  bottom: 0px;
  z-index: 1;
  overflow: hidden;
}

#nav-links {
  display: flex;
  gap: clamp(1rem, 2vw, 2rem);
  margin-top: clamp(2rem, 2vw, 3rem);
  padding: 0rem clamp(1rem, 2vw, 2rem);
  transform: translateY(70%) scale(0.9);
  transition: transform 500ms cubic-bezier(.13, .53, .38, .97);
}

body[data-nav="true"]>nav>#nav-links {
  transform: translateY(0%) scale(1);
}

#nav-links>.nav-link {
  text-decoration: none;
}

#nav-links>.nav-link>.nav-link-label {
  color: white;
  font-size: 1.25rem;
  margin: 0rem;
  text-transform: uppercase;
}

#nav-links>.nav-link>.nav-link-image {
  width: max(20vw, 400px);
  aspect-ratio: 1.8 / 1;
  border-radius: 0.5rem;
  margin-top: 0.75rem;
  object-fit: cover;
}

#nav-toggle {
  height: 5rem;
  width: 5rem;
  position: fixed;
  z-index: 3;
  left: 50%;
  bottom: 3rem;
  transform: translateX(-50%);
  background-color: rgb(182, 142, 113);
  border: none;
  border-radius: 5rem;
  outline: none;
  box-shadow: 0rem 0rem 4rem rgba(0 0 0 / 35%);
  cursor: pointer;
  transition: transform, background-color;
  transition-timing-function: ease;
  transition-duration: 400ms;
}

#nav-toggle:hover {
  transform: translateX(-50%) scale(1.04);
}

#nav-toggle:active {
  transform: translateX(-50%) scale(0.96);
}

body[data-nav="true"]>#nav-toggle {
  background-color: rgb(85, 130, 149);
}

body:not([data-nav="true"])>#nav-toggle:hover>.open {
  opacity: 1;
  transform: translate(-50%, -50%) scale(1);
}

#nav-toggle>i {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%) scale(0.9);
  color: rgb(246, 231, 224);
  font-size: 1.75rem;
  opacity: 0;
  transition: transform, opacity;
  transition-timing-function: ease;
  transition-duration: 400ms;
}

body[data-nav="true"]>#nav-toggle>.close {
  opacity: 1;
  transform: translate(-50%, -50%) scale(1);
}
</style>
