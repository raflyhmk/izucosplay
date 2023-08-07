<template>
  <!-- breadcrumb -->
  <nav aria-label="breadcrumb" class="bg-secondary-subtle">
    <ol class="breadcrumb pt-5 pb-5 container fs-6">
      <li class="breadcrumb-item fw-light">
        <NuxtLink class="text-decoration-none" to="/">Home</NuxtLink>
      </li>
      <li class="breadcrumb-item fw-light">
        <NuxtLink class="text-decoration-none" to="/"
          >Costume products</NuxtLink
        >
      </li>
      <li
        class="breadcrumb-item active fw-bold"
        aria-current="page"
        style="color: #180b39"
      >
        {{ products.namaProduk }}
      </li>
    </ol>
  </nav>
  <!-- end breadcrumb -->

  <!-- deskripsi produk -->
  <div class="container mt-5 mb-4 detailProduk">
    <div class="row">
      <div class="col-sm-12 col-md-12 col-lg-12 col-xl-6">
        <!-- image utama -->
        <img
          :src="products.imageProduk[0].imageUrl"
          class="img-fluid shadow p-3 mb-3 rounded"
          :alt="products.namaProduk"
        />
        <!-- image pendukung -->
        <div class="row">
          <div
            v-for="image in products.imageProduk.slice(1)"
            :key="image.id"
            class="col-sm-2"
          >
            <img
              :src="image.imageUrl"
              :alt="products.namaProduk"
              class="img-thumbnail d-none d-sm-block"
            />
          </div>
        </div>
      </div>
      <div class="col-sm-12 col-md-12 col-lg-12 col-xl-6">
        <h1 class="namaCostume lh-base">
          {{ products.namaProduk }}
          <span class="fw-bold" style="color: #4e3b7f"
            >({{ products.kategoriProduk }})</span
          >
        </h1>
        <h3 class="hargaCostume mt-3 mb-3 fw-bold">
          IDR {{ Intl.NumberFormat().format(products.harga) }}
        </h3>
        <label for="exampleFormControlInput1" class="form-label fs-5"
          >Pilih ukuran</label
        >
        <select class="form-select" name="ukuran">
          <option disabled selected value="" class="fw-light">
            Pilih ukuran
          </option>
          <option value="XS">XS</option>
          <option value="S">S</option>
          <option value="M">M</option>
          <option value="L">L</option>
          <option value="XL">XL</option>
        </select>
        <hr />
        <label for="exampleFormControlInput1" class="form-label fs-5 fw-bold"
          >About the costume</label
        >
        <p v-html="products.deskripsiProduk" class="lh-lg"></p>

        <div class="d-grid gap-2 d-md-flex justify-content-md-start">
          <button
            type="button"
            class="btn btn-izucosplay fw-bold pt-2 pb-2 ps-5 pe-5"
          >
            Beli Kostum
          </button>
          <button
            type="button"
            class="btn btn-izucosplay-outline fw-bold pt-2 pb-2 ps-5 pe-5"
          >
            Sewa kostum
          </button>
        </div>
      </div>
    </div>
  </div>
  <!-- end deskripsi produk -->

  <!-- featured costume -->
  <div class="container mt-5 mb-2">
    <h1 class="title fw-bold">Rekomendasi kostum lainnya</h1>
    <div class="row mt-4">
      <div
        class="listProduk col-sm-12 col-md-12 col-lg-4 mb-3"
        v-for="p in listProducts
          .filter((p) => p.id !== products.id)
          .slice(0, 3)"
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
</template>

<script setup>
const { id } = useRoute().params;

// fetch data from json file (multiple)

const uri =
  "https://my-json-server.typicode.com/raflyhmk/izucosplay-json/produk/" + id;

// fetch data from json file (single)
const { data: listProducts } = await useFetch(
  "https://my-json-server.typicode.com/raflyhmk/izucosplay-json/produk"
);

const { data: products } = await useFetch(uri);
</script>

<style>
[v-cloak] {
  display: none;
}
</style>
