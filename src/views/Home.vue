<template>
  <b-row>
    <b-col cols='8'>
  <div class="home">
    <SongsList msg="Welcome to Ensemble"
      :loggedIn="loggedIn"
      :liked="liked"
      :user="user"
      :friends="friends"
      :feed="feed"
      v-on:new-like="newLike"
    />
  </div>
    </b-col>
  </b-row>
</template>

<script>
// @ is an alias to /src
import SongsList from '@/components/SongsList.vue';

export default {
  name: 'Home',
  components: {
    SongsList,
  },
  data() {
    return {
      isHome: true,
    };
  },
  props: {
    loggedIn: Boolean,
    liked: Array,
    user: Object,
    friends: Object,
    feed: String,
  },
  methods: {
    newLike() {
      this.$emit('new-like');
    },
  },
};
</script>
