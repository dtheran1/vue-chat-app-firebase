<template>
  <nav>
    <div>
      <h1><strong>Vue</strong>Chat App</h1>
    </div>
    <div v-if="isLogin" class="login">
      <Avatar :src="user.photoURL" />
      <button class="text-gray-400 hover:text-white" @click="signOut">
        Sign Out
      </button>
    </div>
    <button v-else class="bg-green-500 hover:bg-green-600" @click="signIn">
        Sign In
    </button>
  </nav>
</template>

<script>
import Avatar from "./Avatar.vue";
import { useAuth } from "@/firebase";
export default {
  components: { Avatar },
  setup() {
    const { user, isLogin, signIn, signOut } = useAuth();
    return { user, isLogin, signIn, signOut };
  },
};
</script>

<style></style>
