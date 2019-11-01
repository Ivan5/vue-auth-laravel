<template>
  <ul>
    <li>
      <router-link :to="{name:'home'}">Home</router-link>
    </li>
    <li>
      <router-link :to="{name:'signin'}">Sign In</router-link>
    </li>
    <template v-if="authenticated">
      <li>{{ user.name }} {{ user.email }}</li>
      <li>
        <router-link :to="{name:'dashboard'}">Dashboard</router-link>
      </li>
      <li>
        <a href="#">Sign Out</a>
      </li>
    </template>
  </ul>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters({
      authenticated: "auth/authenticated",
      user: "auth/user"
    })
  }
};
</script>