<template>
  <q-page class="flex flex-center column">
    <div
      style="
        width: 600px;
        height: 600px;
        background-color: antiquewhite;
        border: 10px solid grey;
        border-radius: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        box-shadow: 4px 10px 20px grey;
      "
    >
      <h3 class="text-bold">Log in to Your account</h3>
      <div class="q-pa-md" style="max-width: 400px">
        <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
          <q-input
            filled
            v-model="name"
            label="Your e-mail"
            hint="E-mail"
            lazy-rules
            :rules="[
              (val) => (val && val.length > 0) || 'Please enter your e-mail',
            ]"
          />

          <q-input
            filled
            v-model="name"
            label="Your password"
            hint="password"
            lazy-rules
            :rules="[
              (val) => (val && val.length > 0) || 'Please enter your password',
            ]"
          />
          <div>
            <q-btn label="Submit" type="submit" color="primary" />
            <q-btn
              label="Reset"
              type="reset"
              color="primary"
              flat
              class="q-ml-sm"
            />
          </div>
        </q-form>
      </div>

      <!-- <table>
        <tr>
          <td>imie</td>
          <td>nazwisko</td>
        </tr>
        <tr v-for="user in Api" v-bind:key="user.UserID">
          <td>{{ user.FirstName }}</td>
          <td>{{ user.LastName }}</td>
        </tr>
      </table> -->
    </div>
  </q-page>
</template>
<script>
import axios from "axios";

export default {
  name: "LoginPage",
  data() {
    return {
      Api: [],
    };
  },
  async created() {
    try {
      const res = await axios.get("http://localhost/API/getUser.php");

      this.Api = res.data;
      console.warn(this.Api);
    } catch (e) {
      console.error(e);
    }
  },
  //   mounted() {
  //     Vue.axios.get("http://localhost/API/getUser.php").then((response) => {
  //       console.warn(response);
  //     });
  //   },
};
</script>
