<template>
  <div class="shotGallery-banner-section">
    <div class="shotGallery-left">
      <img
        :src="shotGalleryPicSrc"
        alt="shotGallery Picture"
        class="shotGallery-pic"
      />
      <div class="shotGallery-info">
        <h2 class="h2">Fahad Chenford</h2>
        <h1 class="h1">
          I’m UX/UI Designer<br />
          at Microtech 👋
        </h1>
      </div>
      <div class="team-logos">
        <h6 class="shotGallery-subtitle">ON TEAMS</h6>
        <img :src="logos" alt="logos" class="logos-img" />
      </div>
      <div class="shotGallery-buttons">
        <q-btn
          class="shotGallery-btn follow-btn"
          :style="{
            backgroundColor: isFollowing ? '#9747FF' : '#f3f3f4',
            color: isFollowing ? 'white' : '#333',
          }"
          @click="toggleFollow"
        >
          <svg
            v-if="!isFollowing"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 640 512"
            class="svg-icon"
          >
            <path
              d="M96 128a128 128 0 1 1 256 0A128 128 0 1 1 96 128zM0 482.3C0 383.8 79.8 304 178.3 304h91.4C368.2 304 448 383.8 448 482.3c0 16.4-13.3 29.7-29.7 29.7H29.7C13.3 512 0 498.7 0 482.3zM504 312V248H440c-13.3 0-24-10.7-24-24s10.7-24 24-24h64V136c0-13.3 10.7-24 24-24s24 10.7 24 24v64h64c13.3 0 24 10.7 24 24s-10.7 24-24 24H552v64c0 13.3-10.7 24-24 24s-24-10.7-24-24z"
            />
          </svg>
          {{ isFollowing ? "Unfollow" : "Follow" }}
        </q-btn>
        <q-btn class="shotGallery-btn hire-me-btn">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 640 512"
            class="svg-icon"
          >
            <path
              d="M88.2 309.1c9.8-18.3 6.8-40.8-7.5-55.8C59.4 230.9 48 204 48 176c0-63.5 63.8-128 160-128s160 64.5 160 128s-63.8 128-160 128c-13.1 0-25.8-1.3-37.8-3.6c-10.4-2-21.2-.6-30.7 4.2c-4.1 2.1-8.3 4.1-12.6 6c-16 7.2-32.9 13.5-49.9 18c2.8-4.6 5.4-9.1 7.9-13.6c1.1-1.9 2.2-3.9 3.2-5.9zM0 176c0 41.8 17.2 80.1 45.9 110.3c-.9 1.7-1.9 3.5-2.8 5.1c-10.3 18.4-22.3 36.5-36.6 52.1c-6.6 7-8.3 17.2-4.6 25.9C5.8 378.3 14.4 384 24 384c43 0 86.5-13.3 122.7-29.7c4.8-2.2 9.6-4.5 14.2-6.8c15.1 3 30.9 4.5 47.1 4.5c114.9 0 208-78.8 208-176S322.9 0 208 0S0 78.8 0 176zM432 480c16.2 0 31.9-1.6 47.1-4.5c4.6 2.3 9.4 4.6 14.2 6.8C529.5 498.7 573 512 616 512c9.6 0 18.2-5.7 22-14.5c3.8-8.8 2-19-4.6-25.9c-14.2-15.6-26.2-33.7-36.6-52.1c-.9-1.7-1.9-3.4-2.8-5.1C622.8 384.1 640 345.8 640 304c0-94.4-87.9-171.5-198.2-175.8c4.1 15.2 6.2 31.2 6.2 47.8l0 .6c87.2 6.7 144 67.5 144 127.4c0 28-11.4 54.9-32.7 77.2c-14.3 15-17.3 37.6-7.5 55.8c1.1 2 2.2 4 3.2 5.9c2.5 4.5 5.2 9 7.9 13.6c-17-4.5-33.9-10.7-49.9-18c-4.3-1.9-8.5-3.9-12.6-6c-9.5-4.8-20.3-6.2-30.7-4.2c-12.1 2.4-24.7 3.6-37.8 3.6c-61.7 0-110-26.5-136.8-62.3c-16 5.4-32.8 9.4-50 11.8C279 439.8 350 480 432 480z"
            />
          </svg>
          Hire Me
        </q-btn>
      </div>
    </div>
    <div class="banner-right">
      <img :src="bannerSrc" alt="Banner" class="banner-img" />
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isFollowing = ref(false);

function toggleFollow() {
  isFollowing.value = !isFollowing.value;
}

const shotGalleryPicSrc = "../../public/images/profilepic.jpeg";
const logos = "../../public/images/logos.png";
const bannerSrc = "../../public/images//bannerpic.png";
</script>

<style scoped>
.shotGallery-banner-section {
  width: 100%;
  height: 554px;
  padding: 0 80px;
  display: flex;
  justify-content: space-between;
  margin-top: 164px;
  align-items: flex-start;
}

.shotGallery-left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 20px;
}

.shotGallery-pic {
  width: 100px;
  height: 100px;
  border-radius: 50%;
}

.shotGallery-info {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.h1 {
  font-family: Inter, sans-serif;
  font-size: 48px;
  font-weight: 800;
  line-height: 1.3;
  text-align: left;
  margin-bottom: 0;
}

.h2 {
  font-family: Inter, sans-serif;
  font-size: 35px;
  font-weight: 700;
  line-height: 1.2;
  text-align: left;
  margin-bottom: 0;
}

.team-logos {
  display: flex;
  align-items: center;
  gap: 10px;
}

.shotGallery-subtitle {
  font-family: "Inter", sans-serif;
  font-size: 18px;
  font-weight: 700;
  line-height: 1.2;
  text-align: left;
  opacity: 0.6;
}

.logos-img {
  width: 50px;
  height: 50px;
}

.shotGallery-buttons {
  display: flex;
  gap: 10px;
}

.shotGallery-btn {
  font-family: "Inter", sans-serif;
  font-size: 14px;
  font-weight: 700;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  padding: 10px 20px;
  border-radius: 4px;
}

.follow-btn {
  background-color: #f3f3f4;
  color: #333;
}

.hire-me-btn {
  background-color: #9747ff;
  color: white;
}

.svg-icon {
  width: 16px;
  height: 16px;
  fill: currentColor;
  margin-right: 5px;
}

.banner-right {
  width: 739px;
  height: 554px;
}

.banner-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media (max-width: 1200px) {
  .shotGallery-banner-section {
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 0 40px;
  }

  .banner-right,
  .banner-img {
    width: 100%;
    height: auto;
  }

  .shotGallery-left {
    align-items: center;
  }

  .h1,
  .h2 {
    text-align: center;
  }

  .shotGallery-buttons {
    flex-direction: column;
    gap: 10px;
  }
  .shotGallery-btn {
    width: 100%;
    height: 45px;
    padding: 10px 15px;
    margin-bottom: 20px;
  }
}

@media (max-width: 768px) {
  .h1 {
    font-size: 35px;
  }

  .h2 {
    font-size: 25px;
  }

  .shotGallery-btn {
    width: 100%;
    height: 45px;
    padding: 10px 15px;
  }
}

@media (max-width: 480px) {
  .shotGallery-pic {
    width: 80px;
    height: 80px;
  }

  .h1 {
    font-size: 28px;
  }

  .h2 {
    font-size: 20px;
  }

  .shotGallery-btn {
    width: 100%;
    height: 40px;
    padding: 8px 10px;
    margin-bottom: 10px;
  }

  .team-logos {
    flex-direction: column;
    gap: 3px;
  }

  .logos-img {
    width: 40px;
    height: 40px;
    margin-bottom: 10px;
  }
}
</style>
