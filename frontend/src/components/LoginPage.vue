<template>
  <div class="offset-white">
  <AppSidebar/>
    <div class="row justify-content-center">
      <h2>
        <strong>Wonder Wake Administration</strong>
      </h2>
    </div>
    <div class="d-flex justify-content-center mt-5">
      <img
        src="@/assets/logo1.png"
        alt="logo image"
        style="
          width: 231.893px;
          height: 233.18px;
          flex-shrink: 0;
          margin-top: 3%;
        "
      />
    </div>
    <div class="px-xl-2 mx-auto mt-5" style="margin-top: 2%">
      <div class="mt-3 mb-3 d-flex flex-column gap-3">
        <label for="email">Email Address</label>
        <br /><br />
        <input
          id="email"
          type="email"
          class="form-control"
          placeholder="Email address"
          style="
            width: 300px;
            height: 10px;
            padding: 13px 15px;
            flex-shrink: 0;
            border-radius: 10px;
            border: 1px solid var(--Text-Normal, #4a4a4a);
            background: #fff;
            font-family: 'Urbanist', sans-serif;
            margin-bottom: 1%;
          "
        />
      </div>
      <div class="mt-5 mb-3 d-flex flex-column gap-3">
        <label for="password">Password</label>
        <br /><br />
        <input
          id="password"
          type="password"
          class="form-control"
          placeholder="Password"
          style="
            width: 300px;
            height: 10px;
            padding: 13px 15px;
            flex-shrink: 0;
            border-radius: 10px;
            border: 1px solid var(--Text-Normal, #4a4a4a);
            background: #fff;
            font-family: 'Urbanist', sans-serif;
          "
        />
      </div>
      <div class="px-xl-2 mx-auto mt-3">
        <button
          class="btn btn-primary d-flex justify-content-center align-items-center gap-2"
          style="
            width: 330px;
            height: 50px;
            padding: 20px 45px;
            border-radius: 10px;
            margin-top: 2%;
            background-color: #4056f4;
            font-size: 16px;
            white-space: nowrap;
            font-style: normal;
            color: #fff;
            line-height: 0.3;
          "
          @click="handleLogin"
        >
          Login To Admin Pannel
        </button>
        <div v-if="error" class="text-danger mt-5 error-message">
          {{ error }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>


export default {

  data() {
    return {
      email: "",
      password: "",
      error: "",
    };
  },
  methods: {
    handleLogin() {
      if (!this.email.trim() || !this.password.trim()) {
        this.error = "Something went wrong. Check email or password";
      } else {
        this.error = "";
        console.log("Email:", this.email);
        console.log("Password:", this.password);
        this.$push({name:"Sidebar"})
      }
    },
  },
};
</script>
<style>
.error-message {
  margin-top: 1%;
  font-family: "Urbanist", sans-serif;
  font-size: 12px;
  font-style: normal;
  font-weight: 300;
  line-height: normal;
  color: #d60411;
}
</style>