<template>
  <Banner v-if="user.bannerFileID" :banner="user.bannerFileID" />
  <div class="content">
    <UserHeader
      :username="`${user.degree} ${user.fullname}`"
      :login="user.login"
      :avatar="user.avatarFileID"
      :isTutor="user.isTutor"
      :description="user.aboutme"
      :icons="user.icons"
    />
    <Filter @setSection="setSection" />
    <!-- <Home :user="user" v-if="currentSection == 0" /> -->
    <Dashboard v-if="currentSection == 1" />
    <Teaching v-if="currentSection == 2" />
    <!-- <Research :user="user" v-if="currentSection == 3" /> -->
    <About :user="user" v-if="currentSection == 4" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Banner from './Banner.vue'
import UserHeader from './Header/UserHeader.vue'
import Filter from './Filter.vue'
// import Home from './Home/Home.vue'
import Dashboard from './Dashboard/Index.vue'
import Teaching from './Teaching/Index.vue'
// import Research from './Research/Research.vue'
import About from './About/About.vue'
import { User } from '@/types/user'

export default defineComponent({
  props: {
    user: Object as () => User,
  },
  components: {
    Banner,
    UserHeader,
    Filter,
    // Home,
    Dashboard,
    Teaching,
    // Research,
    About,
  },
  data() {
    return {
      currentSection: 0,
    }
  },
  methods: {
    setSection(number: number) {
      this.currentSection = number
    },
  },
})
</script>

<style lang="scss" scoped>
@import '@/styles/index.scss';
.content {
  margin: 10px auto;
  width: 1000px;
  max-width: 95vw;
  background-color: #e3e3e3f3;
  color: theme(black);
  margin-top: 30vh;
  padding: 20px;
  border-radius: 20px;
}
</style>
