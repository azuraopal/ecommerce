<template>
  <footer class="bg-gray-800 text-white py-8">
    <div class="container mx-auto flex flex-wrap items-center justify-between">
      <!-- Informasi Toko -->
      <div class="w-full md:w-1/3 lg:w-1/4">
        <h2 class="text-xl font-semibold">KANTIN PPLG 3</h2>
        <p class="mt-2">Kantin pplg 3 adalah kantin yang menjualkan makanan yang lezat dan bergizi</p>
      </div>

      <!-- Navigasi Cepat -->
      <div class="w-full md:w-1/3 lg:w-1/4 mt-4 md:mt-0">
        <h2 class="text-xl font-semibold">Menu</h2>
        <ul class="mt-2">
          <li><router-link to="/" class="text-gray-300 hover:text-white">Home</router-link></li>
          <li><router-link to="/product" class="text-gray-300 hover:text-white">Produk</router-link></li>
          <li><router-link to="/cart" class="text-gray-300 hover:text-white">Keranjang</router-link></li>
          <li><router-link to="/login" class="text-gray-300 hover:text-white">Login</router-link></li>
        </ul>
      </div>

      <!-- Kontak -->
      <div class="w-full md:w-1/3 lg:w-1/4 mt-4 md:mt-0">
        <h2 class="text-xl font-semibold">Hubungi Kami</h2>
        <p class="mt-2">Email: veecommerce@gmail.com</p>
        <p>Telepon: 0858-1904-1101</p>
      </div>
    </div>
  </footer>
</template>

<!-- ... (script dan style tetap sama) -->

