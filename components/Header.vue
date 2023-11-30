<script lang="ts" setup>
import { useAuthStore } from "~/stores/auth";
const authStore = useAuthStore();
const isAuthenticated = ref();
const router = useRouter();

isAuthenticated.value = useCookie("access_token").value;

const logout = async () => {
  await authStore.logout();
  const accessToken = useCookie("access_token");
  const refreshToken = useCookie("refresh_token");
  accessToken.value = null;
  refreshToken.value = null;
  setTimeout(() => {
    isAuthenticated.value = useCookie("access_token").value;
  }, 100);
  router.push({
    path: "/",
  });
};
</script>

<template>
  <header class="w-full border-b bg-gray-700 text-white py-3 md:py-4">
    <div class="container mx-auto">
      <div class="flex flex-wrap items-center justify-between">
        <div class="flex items-center">
          <NuxtLink to="/" class="text-xl font-bold">KANTIN PPLG 3</NuxtLink>
        </div>
        <nav class="flex items-center gap-4 mt-4 md:mt-0">
          <NuxtLink to="/" class="text-base">Home</NuxtLink>
          <NuxtLink to="/product" class="text-base">Products</NuxtLink>
          <NuxtLink to="/cart" class="text-base">Cart</NuxtLink>
          <NuxtLink v-if="!isAuthenticated" to="/login" class="text-base bg-blue-600 px-4 py-2 rounded-lg hover:bg-blue-600/80">Login</NuxtLink>
          <div v-else class="text-base cursor-pointer bg-red-600 px-4 py-2 rounded-lg hover:bg-red-600/80" @click="logout">Logout</div>
        </nav>
      </div>
    </div>
  </header>
</template>
