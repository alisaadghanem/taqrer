<template>
  <div class="shot-item">
    <div class="header">
      <div class="search-box">
        <q-input
          filled
          v-model="searchQuery"
          placeholder="Search"
          dense
          class="custom-search"
          :style="searchBoxStyle"
        >
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
      </div>
      <div class="tabs-container">
        <q-tabs v-model="selectedTab" class="tabs">
          <q-tab
            v-for="(tab, index) in tabs"
            :key="tab"
            :name="tab"
            class="tab-item"
          >
            <span class="tab-text"
              >{{ tab }}
              <span class="tab-number">{{ tabCounts[index] }}</span></span
            >
          </q-tab>
        </q-tabs>
      </div>
      <div class="dropdown">
        <q-select
          v-model="selectedSort"
          :options="sortOptions"
          dense
          outlined
          rounded
          class="custom-dropdown"
          :style="dropdownStyle"
        />
      </div>
    </div>
    <div class="projects-grid">
      <transition-group name="fade-in">
        <q-card
          v-for="project in filteredProjects"
          :key="project.id"
          class="project-card"
        >
          <q-card-section>
            <img
              :src="project.image"
              :alt="project.title"
              class="project-image"
            />
          </q-card-section>
        </q-card>
      </transition-group>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import {
  QInput,
  QIcon,
  QTabs,
  QTab,
  QSelect,
  QCard,
  QCardSection,
} from "quasar";

import img1 from "../../public/images/1.png";
import img2 from "../../public/images/2.png";
import img3 from "../../public/images/3.png";
import img4 from "../../public/images/4.png";
import img5 from "../../public/images/5.png";
import img6 from "../../public/images/6.png";
import img7 from "../../public/images/7.png";
import img8 from "../../public/images/8.png";
import img9 from "../../public/images/9.png";
import img10 from "../../public/images/10.png";
import img11 from "../../public/images/11.png";
import img12 from "../../public/images/12.png";

const searchQuery = ref("");
const selectedTab = ref("All");
const selectedSort = ref("Recent");
const tabs = ["All", "Work", "Projects", "Collections", "Liked Shots"];
const sortOptions = ["Recent", "Popular", "Oldest"];

const projects = ref([
  {
    id: 1,
    title: "Project 1",
    description: "Description 1",
    image: img1,
    type: "Work",
  },
  {
    id: 2,
    title: "Project 2",
    description: "Description 2",
    image: img2,
    type: "Projects",
  },
  {
    id: 3,
    title: "Project 3",
    description: "Description 3",
    image: img3,
    type: "Work",
  },
  {
    id: 4,
    title: "Project 4",
    description: "Description 4",
    image: img4,
    type: "Projects",
  },
  {
    id: 5,
    title: "Project 5",
    description: "Description 5",
    image: img5,
    type: "Collections",
  },
  {
    id: 6,
    title: "Project 6",
    description: "Description 6",
    image: img6,
    type: "Collections",
  },
  {
    id: 7,
    title: "Project 7",
    description: "Description 7",
    image: img7,
    type: "Projects",
  },
  {
    id: 8,
    title: "Project 8",
    description: "Description 8",
    image: img8,
    type: "Work",
  },
  {
    id: 9,
    title: "Project 9",
    description: "Description 9",
    image: img9,
    type: "Work",
  },
  {
    id: 10,
    title: "Project 10",
    description: "Description 10",
    image: img10,
    type: "Projects",
  },
  {
    id: 11,
    title: "Project 11",
    description: "Description 11",
    image: img11,
    type: "Projects",
  },
  {
    id: 12,
    title: "Project 12",
    description: "Description 12",
    image: img12,
    type: "Work",
  },
]);

const tabCounts = computed(() => [200, 11, 5, 45, 123]);

const filteredProjects = computed(() => {
  return projects.value.filter((project) => {
    return (
      (selectedTab.value === "All" || project.type === selectedTab.value) &&
      project.title.toLowerCase().includes(searchQuery.value.toLowerCase())
    );
  });
});

const searchBoxStyle = {
  width: "277px",
  color: "#f1f4f5",
};

const dropdownStyle = {
  width: "147px",
  color: "#d4d7e5",
};
</script>

<style scoped>
.shot-item {
  width: Fixed (1, 440px) px;
  height: Hug (1, 395px) px;
  padding: 0px 80px 0px 80px;
  gap: 30px;
  margin-top: 150px;
  display: flex;
  flex-direction: column;
  margin-bottom: 100px;
}

.header {
  display: flex;
  justify-content: space-between;
  gap: 16px;
  flex-wrap: wrap;
}

.tabs-container {
  flex-grow: 1;
  width: 580px;
  height: 19px;
  gap: 30px;
  text-align: center;
}

.tab-item {
  display: flex;
  align-items: center;
}

.tab-text {
  font-family: Inter, sans-serif;
  font-size: 16px;
  font-weight: 500;
  line-height: 19.36px;
}

.tab-number {
  opacity: 0.4;
  font-family: Inter, sans-serif;
  font-size: 16px;
  font-weight: 400;
  line-height: 19.36px;
  color: #4d4a4a;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(3, auto);
  grid-gap: 30px;
  padding-top: 30px;
}

.project-card {
  width: 100%;
  height: 299px;
  border-radius: 14px;
}

.project-image {
  width: 100%;
  height: 299px;
  border-radius: 14px;
  object-fit: cover;
}

.q-card__section--vert {
  padding: 0px;
}

.custom-search .q-field__control {
  border-radius: 12px !important;
}

.custom-dropdown .q-field__control {
  border-radius: 10px !important;
}

.fade-in-enter-active {
  transition: opacity 0.5s;
}
.fade-in-leave-active {
  transition: opacity 0.5s;
}
.fade-in-enter,
.fade-in-leave-to {
  opacity: 0;
}

@media (max-width: 1200px) {
  .projects-grid {
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    grid-gap: 20px;
  }
  .header {
    flex-direction: column;
    align-items: flex-start;
    padding-top: 50px;
    margin-top: 700px;
  }
  .tabs-container {
    width: 100%;
    order: 2;
  }
  .search-box {
    width: 100%;
    order: 1;
  }
  .dropdown {
    width: 100%;
    order: 3;
    margin-top: 20px;
  }
  .project-card {
    width: 100%;
    height: 100%;
    border-radius: 14px;
  }
  .project-image {
    width: 100%;
    height: 100%;
    border-radius: 14px;
    object-fit: cover;
  }
}

@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  }
  .shot-item {
    padding: 0px 20px 0px 20px;
  }
  .header {
    flex-direction: column;
    align-items: flex-start;
    margin-top: 160px;
    height: 300px;
  }
  .tabs-container,
  .search-box,
  .dropdown {
    width: 100%;
    margin-top: 20px;
  }
  .projects-grid {
    grid-template-columns: repeat(auto-fill, minmax(393px, 1fr));
    grid-template-rows: none;
  }
}

@media (max-width: 480px) {
  .projects-grid {
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  }
  .searchBoxStyle {
    width: 100%;
  }
  .dropdownStyle {
    width: 100%;
  }
}
</style>
