<template>
  <div class="flex">
    <div class="left">
      <SideNavi />
    </div>
    <div class="right">
      <div class="title">
        <p>ユーザー情報</p>
      </div>

      <div v-for="(user, index) in users" :key="index" class="users">
        <div class="flex-users">
          <p class="users-name">{{ user.share }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SideNavi from "../components/SideNavi";
import axios from "axios";
export default {
  data() {
    return {
      users: [
        // {name: 'keiya',},
        // {name: 'keiya',},
        // {name: 'keiya',},
      ]
    };
  },
  async Getshares() {
    const users = await axios 
      .get("https://hidden-refuge-20384.herokuapp.com/api/shares")
      // .then(res => this.users = res.data.data)
      // .then(res => console.log(res))
      console.log(users);
  //   edit() {
  //     if (!this.active) {
  //       axios
  //         .put("https://hidden-refuge-20384.herokuapp.com/api/user", {
  //           email: this.$store.state.user.email,
  //           profile: this.profile,
  //         })
  //         .then((response) => {
  //           this.$store.commit("changeUserData", this.profile);
  //           console.log(response);
  //         });
  //     }
  //     this.active = !this.active;
  //   },
  },
  components: {
    SideNavi,
  },
};
</script>

<style scoped>
.left {
  width: 22%;
  height: 100vh;
}
.right {
  width: 78%;
  height: 100vh;
}
.flex {
  display: flex;
}
.users {
  padding: 20px;
  border-bottom: solid 1px white;
  border-left: 1px solid white;
}
.users-name {
  font-size: 24px;
}
.title {
  border-bottom: 1px solid white;
  border-left: 1px solid white;
  padding: 15px;
}
.title p {
  font-size: 20px;
  font-weight: bold;
}
.flex-users {
  display: flex;
  justify-content: space-between;
}
button {
  width: 100px;
  text-align: center;
  padding: 8px 0 10px;
  color: #fff;
  background-color: #5419da;
  border-radius: 25px;
  display: block;
  margin: 0 0 0 auto;
}
input {
  color: black;
}
</style>