<template>
  <main class="home space">
    <img
      id="logo"
      src="https://avatars.githubusercontent.com/u/72341945?s=400&u=88c5890a3732870a4e2fbc8b6fb420910197cdf3&v=4"
      alt="myPeacewater Link personal branching database research system"
    />
    <h1 style="text-align:center">Peacewater information tree tool</h1>
    <h2>ecocommunity@protonmail.com</h2>
    <ul>
      <li>
        <a href="https://sharaj2.sg-host.com/forum"
        >Peacewater project planning forum</a
        >
      <li>
        <a href="https://scdhub.org/forum"
         >Searchable Database</a
         >
    </ul>

    <div>
      <p>
       Thanks to
               <a href="https://faunadb.com" title="fauna-subscribeble-database">Faunadb</a> and <a href="https://netlify.com" title="netlify build system ci-cd">Netlify</a> 😎
      </p>

      <p>
        
        <a href="https://github.com/chiubaca/vue-netlify-fauna-starter-kit">source code</a>
 
      </p>
    </div>
    <LoginSignup v-if="currentUser === null" />
    <div v-else id="greeting">
      <h2>🖐️ Welcome Back {{ currentUser.user_metadata.full_name }}!</h2>
      <p>
        You're logged in. Go check out your
        <router-link :to="{ name: 'journals' }">journals ➡️ </router-link>.
      </p>
    </div>
    <GithubCorner
      url="https://github.com/chiubaca/vue-netlify-fauna-starter-kit"
    />
  </main>
</template>

<script>
import { mapGetters } from "vuex";
import LoginSignup from "../components/LoginSignup.vue";
import GithubCorner from "../components/GithubCorner.vue";

export default {
  name: "Home",
  components: {
    LoginSignup,
    GithubCorner
  },
  props: {
    msg: String
  },
  data() {
    return {};
  },
  computed: {
    ...mapGetters("auth", ["currentUser"])
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
#greeting {
  border-style: dashed;
  padding: 15px;
  border-radius: 15px;
  border-color: #c6c6c6;
  border-width: 1px;
  h2 {
    text-transform: capitalize;
  }
}
img#logo {
  width: 100%;
  height: auto;
}
</style>
