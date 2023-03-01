<template>
  <q-layout view="lHh Lpr lFf " class="">
    <q-header
      style="
        height: 150px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
      "
      elevated
      class="flex column"
    >
      <q-toolbar>
        <q-toolbar-title> Monthly expenses </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above :width="200" :breakpoint="400">
      <q-scroll-area
        style="
          height: calc(100% - 150px);
          margin-top: 150px;
          border-right: 1px solid #ddd;
        "
      >
        <q-list padding>
          <q-item
            clickable
            v-ripple
            v-for="month in months"
            v-bind:key="month.id"
          >
            <q-item-section avatar>
              <q-icon name="today" class="text-blue" />
            </q-item-section>

            <q-item-section> {{ month.month }} </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>

      <q-img
        class="absolute-top"
        src="https://cdn.quasar.dev/img/material.png"
        style="height: 150px"
      >
        <div class="absolute-bottom bg-transparent">
          <q-avatar size="56px" class="q-mb-sm">
            <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
          </q-avatar>
          <div class="text-weight-bold">Paweł Więzik</div>
          <div>pawel.wiezik@gmail.com</div>
        </div>
      </q-img>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "MainLayout",

  data() {
    return {
      months: [
        {
          id: 0,
          month: "January",
        },
        {
          id: 1,
          month: "February",
        },
        {
          id: 2,
          month: "March",
        },
        {
          id: 3,
          month: "April",
        },
        {
          id: 4,
          month: "May",
        },
        {
          id: 5,
          month: "June",
        },
        {
          id: 6,
          month: "July",
        },
        {
          id: 7,
          month: "August",
        },
        {
          id: 8,
          month: "September",
        },
        {
          id: 9,
          month: "October",
        },
        {
          id: 10,
          month: "November",
        },
        {
          id: 11,
          month: "December",
        },
      ],
    };
  },
});
</script>
