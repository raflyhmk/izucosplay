<template>
  <!-- navbar -->
  <nav class="navbar navbar-expand-lg navbar-light bg-transparent mt-2">
    <div class="container">
      <NuxtLink class="navbar-brand" to="/">
        <img
          src="/image/logo.png"
          alt="Logo"
          class="d-inline-block align-text-top"
        />
      </NuxtLink>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNavDropdown"
        aria-controls="navbarNavDropdown"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav mx-auto">
          <li class="nav-item">
            <NuxtLink class="nav-link" to="/">Home</NuxtLink>
          </li>
          <li class="nav-item dropdown">
            <NuxtLink
              class="nav-link dropdown-toggle"
              to="#"
              id="navbarDropdownMenuLink"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              Our products
            </NuxtLink>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
              <li>
                <NuxtLink class="dropdown-item" to="#">Man cosplay</NuxtLink>
              </li>
              <li>
                <NuxtLink class="dropdown-item" to="#">Woman cosplay</NuxtLink>
              </li>
              <li>
                <NuxtLink class="dropdown-item" to="#"
                  >Wig/Accessories</NuxtLink
                >
              </li>
              <li>
                <NuxtLink class="dropdown-item" to="#">Weapon Replica</NuxtLink>
              </li>
            </ul>
          </li>
          <li class="nav-item">
            <NuxtLink class="nav-link" to="#">Gallery</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink class="nav-link" to="#">Reviews</NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink class="nav-link" to="#">About us</NuxtLink>
          </li>
        </ul>
        <NuxtLink to="#"
          ><i class="fa-solid fa-cart-shopping"
            ><span>cart 0</span></i
          ></NuxtLink
        >
      </div>
    </div>
  </nav>
  <!-- end navbar -->
  <!-- content -->
  <div>
    <slot />
  </div>
  <!-- end content -->
  <!-- footer -->
  <footer>
    <div class="container mt-3">
      <div class="row">
        <div class="col-sm-12 col-md-4 mb-3 align-items-center">
          <img src="/image/logo.png" alt="logo" class="img-fluid border-0" />
          <p class="descToko fw-normal mt-2">
            From Fan to Cosplayer and now discover, explore, and find the
            perfect cosplay costume for you!
          </p>
          <div class="kontakToko">
            <a to="#"><i class="fa-brands fa-facebook"></i></a>
            <a to="#"><i class="fa-brands fa-instagram"></i></a>
            <a to="#"><i class="fa-brands fa-whatsapp"></i></a>
          </div>
        </div>
        <div class="col-sm-12 col-md-2 offset-md-1 align-self-center">
          <h5 class="daftarProduk mb-4">Quick Links</h5>
          <p class="listProduk fw-normal"><a htoef="#">Home</a></p>
          <p class="listProduk fw-normal"><a to="#">Kostum</a></p>
          <p class="listProduk fw-normal"><a to="#">Payment channel</a></p>
          <p class="listProduk fw-normal"><a to="#">FAQ</a></p>
        </div>
        <div class="col-sm-12 col-md-4 offset-md-1 mb-2 align-self-center">
          <h5 class="titleSubscribe">Subscribe to us</h5>
          <p class="descSubscribe fw-light">
            Dengan berlangganan kepada kami, para cosplayer akan mendapatkan
            informasi terbaru mengenai berbagai macam kostum baru yang kami
            punya.
          </p>
          <div class="input-group">
            <input
              type="email"
              class="form-control form-subscribe"
              id="subscribe"
              placeholder="masukan email mu..."
              aria-describedby="subscribeHelp"
            />
            <span class="input-group-btn">
              <button
                class="btn btn-izucosplay fs-6 pt-2 pb-2 ps-4 pe-4"
                type="button"
              >
                Subscribe!
              </button>
            </span>
          </div>
        </div>
      </div>
    </div>
    <div class="CP-footer d-flex justify-content-center mt-3">
      <h5>
        Copyright © 2023 All rights reserved by
        <span class="fw-bold" style="color: #4e3b7f">IzuCosplay Team</span>
      </h5>
    </div>
  </footer>
  <!-- end footer -->
</template>

<script setup>
useHead({
  title: "figuartz",
  link: [
    // bootstrap css
    {
      href: "https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/css/bootstrap.min.css",
      rel: "stylesheet",
      integrity:
        "sha384-4bw+/aepP/YC94hEpVNVgiZdgIC5+VKNBQNGCHeKRQN+PtmoHDEXuppvnDJzQIu9",
      crossorigin: "anonymous",
    },
    // css styling
    {
      href: "/css/style.css",
      rel: "stylesheet",
    },
    // favicon
    {
      rel: "shortcut icon",
      href: "/image/favicon.png",
      type: "image/png",
    },
    // font google
    {
      rel: "preconnect",
      href: "https://fonts.googleapis.com",
    },
    {
      rel: "preconnect",
      href: "https://fonts.gstatic.com",
    },
    {
      href: "https://fonts.googleapis.com/css2?family=Bitter:wght@100;200;300;400;500;600;700&display=swap",
      rel: "stylesheet",
    },
  ],
  script: [
    {
      src: "https://cdn.jsdelivr.net/npm/bootstrap@5.3.1/dist/js/bootstrap.bundle.min.js",
      integrity:
        "sha384-HwwvtgBNo3bZJJLYd8oVXjrBZt8cqVSpeBNS5n7C8IVInixGAoxmnlMuBnhbgrkm",
      crossorigin: "anonymous",
    },
    {
      src: "https://kit.fontawesome.com/6a4ade49be.js",
      crossorigin: "anonymous",
    },
  ],
});
</script>
