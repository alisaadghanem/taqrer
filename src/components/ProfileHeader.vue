<template>
  <q-header class="bg-white text-black">
    <q-toolbar>
      <!-- Logo -->
      <q-toolbar-title class="logo">taqrer</q-toolbar-title>

      <!-- Toggle Drawer Button (for mobile) -->
      <q-btn
        class="q-mr-sm"
        flat
        round
        dense
        icon="menu"
        @click="drawer = !drawer"
        aria-label="Toggle navigation drawer"
        v-if="$q.screen.lt.sm"
      />

      <!-- Navigation Links (in Drawer) -->
      <q-drawer
        v-model="drawer"
        show-if-above
        bordered
        side="left"
        content-class="bg-white"
      >
        <q-item>
          <q-item-section avatar>
            <q-avatar
              square
              style="border-radius: 50%; width: 45px; height: 45px"
              class="q-ml-md"
            >
              <img :src="profilePic" alt="Profile Picture" />
            </q-avatar>
          </q-item-section>
          <q-item-section>
            <q-btn
              class="upload-button q-ml-md"
              no-caps
              style="
                min-width: 105px;
                height: 45px;
                border-radius: 12px;
                background-color: #9747ff;
                color: white;
                font-family: 'Inter', sans-serif;
                font-size: 14px;
                font-weight: 500;
                text-align: center;
                display: flex;
                justify-content: center;
                align-items: center;
              "
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 448 512"
                style="width: 18px; height: 18px; margin-right: 4px"
              >
                <path
                  d="M246.6 9.4c-12.5-12.5-32.8-12.5-45.3 0l-128 128c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 109.3 192 320c0 17.7 14.3 32 32 32s32-14.3 32-32l0-210.7 73.4 73.4c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3l-128-128zM64 352c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 64c0 53 43 96 96 96l256 0c53 0 96-43 96-96l0-64c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 64c0 17.7-14.3 32-32 32L96 448c-17.7 0-32-14.3-32-32l0-64z"
                  fill="white"
                />
              </svg>
              <span>Upload</span>
            </q-btn>
          </q-item-section>
        </q-item>
        <q-list link inset-delimiter>
          <q-item v-for="item in navItems" :key="item.name" clickable>
            <q-item-section>
              <q-item-label>{{ item.label }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-list>
      </q-drawer>

      <!-- Navigation Links (in Toolbar for larger screens) -->
      <q-tabs
        v-model="tab"
        class="text-black q-pt-none q-pb-none col-md-6"
        indicator-color="primary"
        v-if="$q.screen.gt.sm"
      >
        <q-tab
          v-for="item in navItems"
          :key="item.name"
          :name="item.name"
          :label="item.label"
        />
      </q-tabs>

      <!-- Button and Profile -->
      <div
        class="row items-center col-xs-6 col-md-3 justify-end"
        v-if="$q.screen.gt.sm"
      >
        <q-avatar
          square
          style="border-radius: 50%; width: 45px; height: 45px"
          class="q-ml-md"
        >
          <img :src="profilePic" alt="Profile Picture" />
        </q-avatar>
        <q-btn
          class="upload-button q-ml-md"
          no-caps
          style="
            min-width: 105px;
            height: 45px;
            border-radius: 12px;
            background-color: #9747ff;
            color: white;
            font-family: 'Inter', sans-serif;
            font-size: 14px;
            font-weight: 500;
            text-align: center;
            display: flex;
            justify-content: center;
            align-items: center;
          "
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 448 512"
            style="width: 18px; height: 18px; margin-right: 4px"
          >
            <path
              d="M246.6 9.4c-12.5-12.5-32.8-12.5-45.3 0l-128 128c-12.5 12.5-12.5 32.8 0 45.3s32.8 12.5 45.3 0L192 109.3 192 320c0 17.7 14.3 32 32 32s32-14.3 32-32l0-210.7 73.4 73.4c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3l-128-128zM64 352c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 64c0 53 43 96 96 96l256 0c53 0 96-43 96-96l0-64c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 64c0 17.7-14.3 32-32 32L96 448c-17.7 0-32-14.3-32-32l0-64z"
              fill="white"
            />
          </svg>
          <span>Upload</span>
        </q-btn>
      </div>
    </q-toolbar>
  </q-header>
</template>

<script setup>
import { ref } from "vue";
import profilePic from "src/assets/profilepic.jpeg";

const drawer = ref(false);

const navItems = [
  { name: "inspiration", label: "Inspiration" },
  { name: "find-work", label: "Find Work" },
  { name: "learn-design", label: "Learn Design" },
  { name: "go-pro", label: "Go Pro" },
  { name: "hire-designers", label: "Hire Designers" },
];
</script>

<style scoped>
.logo {
  font-family: "Pacifico", cursive;
  font-size: 40px;
  font-weight: 400;
  line-height: 70.24px;
  text-align: left;
}

.bg-white {
  width: 100%;
  height: auto;
  padding: 17px 30px;
  border-bottom: 1px solid #ebeaea;
  justify-content: space-between;
}

@media (max-width: 600px) {
  .logo {
    font-size: 30px;
    line-height: 50px;
  }
  .upload-button {
    font-size: 12px;
    min-width: 85px;
    height: 35px;
  }
  .q-avatar {
    width: 35px;
    height: 35px;
  }
}
</style>
