<template>
  <div class="component">
    <h1>The User Component</h1>
    <p>I'm an awesome User!</p>
    <p>User ID is: {{ userID }}</p>
    <p>User Name is: {{ userData.name }} | Status: {{ userData.status }}</p>
    <button @click="changeUserID">change id</button>
    <button @click="changeUserData">change data</button>
    <hr />
    <div class="row">
      <div class="col-xs-12 col-sm-6">
        <app-user-details
          :UserID="userID"
          @update:UserID="userID = $event"
          :UserData="userData"
          @update:UserData="userData = $event">
        </app-user-details>
      </div>
      <div class="col-xs-12 col-sm-6">
        <app-user-edit></app-user-edit>
      </div>
    </div>
  </div>
</template>

<script>
import UserDetails from "./UserDetails.vue";
import UserEdit from "./UserEdit.vue";

export default {
  data() {
    return {
      userID: 0,
      userData: {
        name: 'Omar Hegazi',
        status: 'Unknowen'
      }
    }
  },
  methods: {
    changeUserID() {
      this.userID = 10;
    },
    changeUserData() {
      this.userData.name = 'Mero Gazi'
      this.userData.status = 'Online'
    }
  },
  components: {
    appUserDetails: UserDetails,
    appUserEdit: UserEdit,
  },
};
</script>

<style >
div {
  background-color: lightblue;
}
</style>
