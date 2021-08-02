<template>
  <div>
    <div class="left-padding">
      <img class="logo" src="../assets/logo.png" />
      <div class="flex icon-field">
        <img class="icon" src="../assets/home.png" />
        <p @click="$router.push('/home')">ホーム</p>
        <!-- <i class="fas fa-dog fa-flip-horizontal	"></i> -->
      </div>
      <div class="flex icon-field">
        <img class="icon" src="../assets/profile.png"/>
        <p @click="$router.push('/profile')">プロフィール</p>
      </div>
      <div class="flex icon-field">
        <img class="icon" src="../assets/logout.png" />
        <p @click="$router.push('/')">ログアウト</p>
      </div>
      <div class="flex icon-field">
        <i class="fas fa-users"></i>
        <p @click="$router.push('/users')">ユーザー情報</p>
      </div>
    </div>
    <ShareMessage/>
  </div>
</template>

<script>
import ShareMessage from "../components/ShareMessage";
export default { 
  components: {
    ShareMessage
  }
};
</script>

<style scoped>
.left-padding {
  margin: 20px;
}
.flex {
  display: flex;
}
.logo {
  width: 100px;
}
.icon-field {
  margin-top: 15px;
  cursor: pointer;
}
.icon {
  width: 25px;
}
.icon-field p {
  font-size: 16px;
  padding-left: 15px;
}
.fas {
  width: 25px;
  font-size: 20px
}
</style>