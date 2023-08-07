<template>
  <!-- jumbotron -->
  <div class="jumbotron text-center d-flex align-items-center mb-2">
    <div class="container">
      <h1 class="display-4 text-white">
        From Fan to
        <span class="fw-bold highlight" style="color: #c6b5f1">Cosplayer</span
        ><br />
        Find the Right
        <span class="fw-bold highlight" style="color: #c6b5f1"
          >Cosplay Costume</span
        >
        for You.
      </h1>
      <button
        type="button"
        class="btn btn-izucosplay fw-bold mt-3 pt-2 pb-2 ps-5 pe-5"
      >
        Belanja sekarang
      </button>
    </div>
  </div>
  <!-- end jumbotron -->

  <!-- category profile -->
  <div class="container category mt-5 mb-2">
    <h1 class="title text-capitalize mb-4 fw-bold">our category</h1>
    <div class="row">
      <div class="col-sm-12 col-md-6 col-lg-3 mb-4 mb-sm-4 mb-lg-0">
        <div class="card text-bg-dark border-0">
          <img
            src="/image/woman-cosplay.jpg"
            class="card-img img-fluid"
            alt="woman cosplay"
          />
          <div class="card-img-overlay d-flex align-items-end">
            <button
              type="button"
              class="btn btn-izucosplay fw-bold d-flex align-items-center justify-content-center"
            >
              Woman cosplay<i class="fa-solid fa-angle-right ps-3"></i>
            </button>
          </div>
        </div>
      </div>
      <div class="col-sm-12 col-md-6 col-lg-3 mb-4 mb-sm-4 mb-lg-0">
        <div class="card text-bg-dark border-0">
          <img
            src="/image/man-cosplay.jpg"
            class="card-img img-fluid"
            alt="man cosplay"
          />
          <div
            class="card-img-overlay d-flex align-items-end justify-content-center"
          >
            <button
              type="button"
              class="btn btn-izucosplay fw-bold d-flex align-items-center justify-content-center"
            >
              Man cosplay<i class="fa-solid fa-angle-right ps-3"></i>
            </button>
          </div>
        </div>
      </div>
      <div class="col-sm-12 col-md-12 col-lg-6 mb-4 mb-sm-4 mb-lg-0">
        <div class="col-12 mb-3">
          <div class="card text-bg-dark border-0">
            <img
              src="/image/wig-aksesoris.jpg"
              class="card-img img-fluid"
              alt="woman cosplay"
            />
            <div
              class="card-img-overlay d-flex align-items-end justify-content-start"
            >
              <button
                type="button"
                class="btn btn-izucosplay fw-bold d-flex align-items-center justify-content-center"
              >
                Wig / Accessories<i class="fa-solid fa-angle-right ps-3"></i>
              </button>
            </div>
          </div>
        </div>
        <div class="col-12">
          <div class="card text-bg-dark border-0">
            <img
              src="/image/weapon-replica.jpg"
              class="card-img img-fluid"
              alt="woman cosplay"
            />
            <div
              class="card-img-overlay d-flex align-items-end justify-content-start"
            >
              <button
                type="button"
                class="btn btn-izucosplay fw-bold d-flex align-items-center justify-content-center"
              >
                Weapon Replica 1:1<i class="fa-solid fa-angle-right ps-3"></i>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- end category profile -->

  <!-- featured costume -->
  <div class="container mt-5 mb-2">
    <div class="row">
      <div
        class="col-12 col-lg-5 d-flex justify-content-start align-items-center"
      >
        <h1 class="title fw-bold">Featured costume</h1>
      </div>
      <div class="col-0 col-lg-7 d-flex justify-content-end align-items-center">
        <button
          type="button"
          class="btn btn-primary btn-izucosplay d-none d-lg-block pt-2 pb-2 ps-4 pe-4"
        >
          Lihat semua<i class="fa-solid fa-angle-right ps-3"></i>
        </button>
      </div>
    </div>
    <div class="row mt-4">
      <div
        class="listProduk col-sm-12 col-md-12 col-lg-4 mb-3"
        v-for="p in products.slice(0, 3)"
        :key="p"
      >
        <NuxtLink :to="`/costume/${p.id}`" style="text-decoration: none">
          <img
            :src="p.imageProduk[0].imageUrl"
            class="img-fluid shadow p-3 mb-3 rounded"
          />
          <div class="row">
            <div class="col-9 col-xl-10">
              <h1 class="titleProduk fw-medium mt-2 text-md-start lh-base">
                {{ p.namaProduk }}
                <span
                  style="font-weight: 700; color: #4e3b7f"
                  class="text-capitalize"
                >
                  ({{ p.kategoriProduk }})</span
                >
              </h1>
              <h3 class="hargaProduk mt-2 fw-bold text-md-start">
                IDR {{ Intl.NumberFormat().format(p.harga) }}
              </h3>
            </div>
            <div class="col-3 col-xl-2 d-flex align-items-center">
              <i class="fa-solid fa-bag-shopping text-md-start"></i>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
  <!-- end featured costume -->

  <!-- gallery -->
  <div class="container category mt-5 mb-2">
    <div class="row">
      <div
        class="col-12 col-lg-5 d-flex justify-content-start align-items-center"
      >
        <h1 class="title fw-bold">Gallery of Our Cosplayer</h1>
      </div>
      <div class="col-0 col-lg-7 d-flex justify-content-end align-items-center">
        <button
          type="button"
          class="btn btn-primary btn-izucosplay d-none d-lg-block pt-2 pb-2 ps-4 pe-4"
        >
          Cosplayer lain<i class="fa-solid fa-angle-right ps-3"></i>
        </button>
      </div>
    </div>
    <div class="row mt-4">
      <div class="col-sm-12 col-md-12 col-lg-6 mb-4 mb-sm-4 mb-lg-0">
        <div class="col-12 mb-3">
          <div class="card text-bg-dark border-0">
            <img
              src="/image/galeri-1.jpg"
              class="card-img"
              alt="galeri cosplayer"
            />
          </div>
        </div>
        <div class="col-12">
          <div class="card text-bg-dark border-0">
            <img
              src="/image/galeri-2.jpg"
              class="card-img"
              alt="galeri cosplayer"
            />
          </div>
        </div>
      </div>
      <div
        class="col-sm-12 col-md-6 col-lg-3 mb-4 mb-sm-4 mb-lg-0 order-first order-md-last"
      >
        <div class="card text-bg-dark border-0">
          <img
            src="/image/galeri-3.jpg"
            class="card-img"
            alt="galery cosplayer"
          />
        </div>
      </div>
      <div
        class="col-sm-12 col-md-6 col-lg-3 mb-4 mb-sm-4 mb-lg-0 order-first order-md-last"
      >
        <div class="card text-bg-dark border-0">
          <img
            src="/image/galeri-4.jpg"
            class="card-img"
            alt="galeri cosplayer"
          />
        </div>
      </div>
    </div>
  </div>
  <!-- end gallery -->

  <!-- testimoni -->
  <div class="container mt-5 mb-2">
    <h1 class="title text-capitalize mb-4 fw-bold">What our cosplayer said</h1>
    <div class="row align-items-center">
      <div class="col-12 col-sm-12 col-md-6 mb-4 mb-lg-0 mt-3 mt-md-0">
        <h5 class="datetime d-flex justify-content-end fw-normal">
          7 hari yang lalu
        </h5>
        <p class="isiTestimoni mt-0 mt-lg-4 fw-normal fs-4">
          Bahannya bagus banget dan kualitasnya juga tahan lama. kostum nya
          dipacking rapi dan menarik. Ukurannya juga pas untuk cosplaying.
          overall saya enggak nyesel deh beli kostum cosplay disini. Thank you.
          ❤️.
        </p>
        <div class="row mb-2">
          <div class="col-10">
            <h3 class="reviewer fw-bold">Brandon Stanton</h3>
            <span class="subReviewer fs-5">Cosplayer Ayato</span>
          </div>
          <div class="col-2 d-flex align-items-center">
            <i class="fa-solid fa-star fa-2xl"
              ><span class="text-secondary-emphasis ms-2 fs-3">4.8</span></i
            >
          </div>
        </div>
        <button
          type="button"
          class="btn btn-izucosplay fw-bold mt-3 pt-2 pb-2 ps-5 pe-5 d-none d-lg-block"
        >
          Testimonial lainnya<i class="fa-solid fa-angle-right ps-3"></i>
        </button>
      </div>
      <div
        class="col-12 col-sm-12 col-md-5 offset-md-1 order-first order-md-last"
      >
        <img
          src="/image/testimonial.jpg"
          alt="testimonial"
          class="img-fluid rounded"
        />
      </div>
    </div>
  </div>
  <!-- end testimoni -->

  <!-- google maps -->
  <div class="container maps mt-5">
    <center>
      <h1 class="title fs-3 mb-3">Kunjungi toko kami secara langsung yuk!</h1>
      <p class="descTitle fs-6 mb-3 col-12 col-lg-6">
        Para cosplayer bisa mengunjungi toko kami secara langsung untuk melihat
        kondisi kostum secara langsung, lokasi kami bisa dilihat di maps yang
        ada di bawah ini.
      </p>
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d15810.575997353662!2d110.3970178!3d-7.8274513!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xaad77b93e39dc1d2!2sAnigame!5e0!3m2!1sid!2sid!4v1666768849626!5m2!1sid!2sid"
        style="border: 0"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        class="mb-4"
      ></iframe>
    </center>
  </div>
  <!-- end google maps -->
</template>

<script setup>
// fetch data from json file
const { data: products } = await useFetch(
  "https://my-json-server.typicode.com/raflyhmk/izucosplay-json/produk"
);

console.log(products.value);
</script>
