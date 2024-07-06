<template>
  <div class="bg-white text-primary">
    <div class="row items-center">
      <!-- Logo and Description Column -->
      <div class="col-xs-12 col-md-2">
        <div class="logo">
          <q-toolbar-title class="logo-text">taqrer</q-toolbar-title>
          <div class="logo-description">
            <p>
              Taqrer is the world's leading community for creatives to share,
              grow, and get hired.
            </p>
          </div>
          <img src="/images/icons.png" alt="Description Image" class="footer-image" />
        </div>
      </div>

      <!-- Sections Column -->
      <div class="col-xs-13 col-md-10">
        <div class="footer-sections row">
          <div class="footer-column">
            <q-toolbar-title class="footer-title">For Designers</q-toolbar-title>
            <div class="footer-content">
              <p>Go pro!</p>
              <p>Explore design work</p>
              <p>Design blog</p>
            </div>
          </div>

          <div class="footer-column">
            <q-toolbar-title class="footer-title">Hire Designers</q-toolbar-title>
            <div class="footer-content">
              <p>Post a job opening</p>
              <p>Post a freelance project</p>
              <p>Search for designers</p>
            </div>
          </div>

          <div class="footer-column">
            <q-toolbar-title class="footer-title">Company</q-toolbar-title>
            <div class="footer-content">
              <p>About</p>
              <p>Careers</p>
              <p>Support</p>
              <p>Media kit</p>
              <p>Testimonials</p>
            </div>
          </div>

          <div class="footer-column">
            <q-toolbar-title class="footer-title">Directories</q-toolbar-title>
            <div class="footer-content">
              <p>Design jobs</p>
              <p>Designers for hire</p>
              <p>Freelance designers<br />for hire</p>
              <p>Tags</p>
              <p>Places</p>
            </div>
          </div>

          <div class="footer-column">
            <q-toolbar-title class="footer-title">Design Resources</q-toolbar-title>
            <div class="footer-content">
              <p>Freelancing</p>
              <p>Design Hiring</p>
              <p>Design Portfolio</p>
              <p>Design Education</p>
              <p>Creative Process</p>
              <p>Design Industry<br />Trends</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Line above copyright and shots -->
    <div class="footer-line"></div>

    <div class="footer-bottom">
      <p class="copyright">
        <span>© 2023 taqrer. All rights reserved</span>
        <span class="flexible-shots">
          21,160,075 <span class="flexible-text">shots flexibble</span>
        </span>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style scoped>
.bg-white {
  background-color: #fafafb !important;
  width: 100%;
  padding: 80px;
  box-sizing: border-box;
}

.logo {
  display: flex;
  flex-direction: column;
  margin-bottom: 90px;
}

.logo-text {
  font-family: "Pacifico", cursive;
  font-size: 40px;
  color: #9747ff;
  margin-bottom: 5px;
}

.logo-description {
  opacity: 0.7;
  font-family: Inter, sans-serif;
  font-size: 14px;
  color: #000000;
  margin-bottom: 20px;
}

.footer-sections {
  display: flex;
  flex-wrap: wrap;
  margin-left: 150px;
  width: 100%;
}

.footer-column {
  margin-right: 30px;
}

.footer-image {
  width: 95px;
  height: 18px;
  margin-top: 8px;
}

.footer-title {
  font-family: Inter, sans-serif;
  font-size: 14px;
  font-weight: 600;
  line-height: 23.8px;
  text-align: left;
  width: 160px;
  color: #000000;
  margin-bottom: 20px;
}

.footer-content {
  font-family: Inter, sans-serif;
  font-size: 14px;
  color: #000000;
}

.footer-line {
  width: 100%;
  border-top: 1px solid #d9d9d9;
  margin: 30px 0;
}

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footer-bottom .copyright {
  color: #000000;
}

.footer-bottom .flexible-shots {
  font-family: Inter, sans-serif;
  font-size: 14px;
  font-weight: 600;
  color: #000000;
  margin-left: auto;
}

.flexible-text {
  font-family: Inter, sans-serif;
  font-size: 14px;
  font-weight: 400;
  line-height: 23.8px;
  text-align: left;
  opacity: 0.6;
}

@media (max-width: 1920px) {
  .bg-white {
    padding: 60px;
  }

  .footer-sections {
    margin-left: 100px;
  }

  .footer-bottom .flexible-shots {
    margin-left: 850px;
  }
}

@media (max-width: 1200px) {
  .bg-white {
    padding: 40px;
  }

  .logo {
    display: flex;
    flex-direction: column;
    margin-bottom: 70px;
  }

  .footer-sections {
    margin-left: 70px;
  }

  .footer-bottom .flexible-shots {
    margin-left: 600px;
  }
}

@media (max-width: 768px) {
  .footer-bottom {
    flex-direction: column;
    align-items: flex-start;
  }

  .footer-sections {
    margin-left: 0px;
  }

  .footer-bottom .flexible-shots {
    margin-left: 90px;
    margin-top: 10px;
  }

  .footer-column {
    flex: 1 1 100%;
    margin-top: 20px;
  }
}

@media (max-width: 480px) {
  .logo-description p {
    line-height: 1.2;
  }

  .footer-sections {
    margin-left: 0px;
  }

  .footer-content p {
    line-height: 1.2;
  }

  .footer-bottom .flexible-shots {
    font-size: 12px;
  }

  .flexible-text {
    font-size: 12px;
  }
}
</style>
