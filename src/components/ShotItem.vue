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
          class="custom-dropdown"
          :style="dropdownStyle"
        />
      </div>
    </div>
    <div class="projects-grid">
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
    image: "src/assets/1.png",
    type: "Work",
  },
  {
    id: 2,
    title: "Project 2",
    description: "Description 2",
    image: "src/assets/2.png",
    type: "Projects",
  },
  {
    id: 3,
    title: "Project 3",
    description: "Description 3",
    image: "src/assets/3.png",
    type: "Work",
  },
  {
    id: 4,
    title: "Project 4",
    description: "Description 4",
    image: "src/assets/4.png",
    type: "Projects",
  },
  {
    id: 5,
    title: "Project 5",
    description: "Description 5",
    image: "src/assets/5.png",
    type: "Collections",
  },
  {
    id: 6,
    title: "Project 6",
    description: "Description 6",
    image: "src/assets/6.png",
    type: "Work",
  },
  {
    id: 7,
    title: "Project 7",
    description: "Description 7",
    image: "src/assets/7.png",
    type: "Projects",
  },
  {
    id: 8,
    title: "Project 8",
    description: "Description 8",
    image: "src/assets/8.png",
    type: "Work",
  },
  {
    id: 9,
    title: "Project 9",
    description: "Description 9",
    image: "src/assets/9.png",
    type: "Work",
  },
  {
    id: 10,
    title: "Project 10",
    description: "Description 10",
    image: "src/assets/10.png",
    type: "Projects",
  },
  {
    id: 11,
    title: "Project 11",
    description: "Description 11",
    image: "src/assets/11.png",
    type: "Projects",
  },
  {
    id: 12,
    title: "Project 12",
    description: "Description 12",
    image: "src/assets/12.png",
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
  grid-template-columns: repeat(auto-fill, minmax(393px, 1fr));
  grid-gap: 30px;
  padding-top: 30px;
}

.project-card {
  width: 393px;
  height: 299px;
  border-radius: 14px;
}

.project-image {
  width: 393px;
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

/* Media Queries for responsiveness */

@media (max-width: 1200px) {
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
  .shot-item {
    padding: 0px 20px 0px 20px;
  }
  .header {
    flex-direction: column;
    align-items: flex-start;
    margin-top: 270px;
    height: 300px;
  }
  .tabs-container,
  .search-box,
  .dropdown {
    width: 100%;
    margin-top: 20px;
  }
}

@media (max-width: 480px) {
  .searchBoxStyle {
    width: 100%;
  }
  .dropdownStyle {
    width: 100%;
  }
}
</style>
