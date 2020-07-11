<script>
export default {
  props: {
    social: {
      type: Object,
      requried: true
    }
  },
  data() {
    return {
      open: false,
    }
  },
  methods: {
    openLinks() {
      this.open = true;
      this.$refs["container"].classList.add("open");
    },
    closeLinks() {
      this.open = false;
      this.$refs["container"].classList.remove("open");
    }
  },
  computed: {
    style() {
      if(this.open) {
        let size = Object.keys(this.social).length * 88;
        if(size < 230) {
          size = 230;
        }
        return `width: ${size}px;`;
      } else {
        return '';
      }
    }
  }
};
</script>

<template>
  <div class="body">
    <div class="container" id="container" ref="container" :style.sync="style">
      <button @click="openLinks" class="open-btn">
        <i class="fas fa-share-alt"></i>
      </button>
      <a href="#" class="x" id="close" @click="closeLinks">
        <button @click="openLinks" class="close-btn">
          <i class="fas fa-times"></i>
        </button>
      </a>
      <a :href="`https://youtube.com/c/${social.youtube}`" v-if="social && social.youtube" class="ytb" target="_blank">
        <i class="fab fa-youtube"></i>
      </a>
      <a :href="`https://twitter.com/${social.twitter}`" v-if="social && social.twitter" class="twt" target="_blank">
        <i class="fab fa-twitter"></i>
      </a>
      <a :href="`https://linkedin.com/in/${social.linkedin}`" v-if="social && social.linkedin" class="lin" target="_blank">
        <i class="fab fa-linkedin"></i>
      </a>
      <a :href="`https://instagram.com/${social.instagram}`" v-if="social && social.instagram" class="ins" target="_blank">
        <i class="fab fa-instagram"></i>
      </a>
      <a :href="`https://github.com/${social.github}`" v-if="social && social.github" class="git" target="_blank">
        <i class="fab fa-github"></i>
      </a>
      <a :href="`https://facebook.com/${social.facebook}`" v-if="social && social.facebook" class="fcb" target="_blank">
        <i class="fab fa-facebook"></i>
      </a>
    </div>
  </div>
</template>

<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.10.2/css/all.min.css");
@import url("https://fonts.googleapis.com/css?family=Muli&display=swap");

.container {
  background-color: #fff;
  border-radius: 50px;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  transition: 0.4s ease;
  height: 70px;
  width: 70px;
}

.container.open {
  width: 438px;
}

.container .open-btn {
  position: absolute;
  top: 0;
  left: 0;

  background-image: linear-gradient(
    110.1deg,
    rgba(241, 115, 30, 1) 18.9%,
    rgba(231, 29, 54, 1) 90.7%
  );
  color: #fff;
  cursor: pointer;
  border: 0;
  border-radius: 50%;
  font-size: 26px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
  height: 70px;
  width: 70px;
  z-index: 100;
}

.container .close-btn {
  background-color: #282c37;
  position: absolute;
  top: 0;
  left: 0;
  cursor: pointer;
  border: 0;
  font-size: 26px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
  height: 70px;
  width: 70px;
  z-index: 100;
}

.container.open .open-btn {
  display: none;
}

.container a {
  background-color: #fff;
  border-radius: 50%;
  font-size: 26px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  top: 0;
  left: 0;
  margin: 10px;
  height: 50px;
  width: 50px;
  text-decoration: none;
  opacity: 0;
}

.container.open a {
  position: static;
  opacity: 1;
  transition: 0.4s ease;
}

.container a.ytb {
  background-color: #ff0000;
}
.container a.twt {
  background-color: #1da1f2;
}
.container a.lin {
  background-color: #007bb5;
}
.container a.ins {
  background-color: #c32aa3;
}
.container a.git {
  background-color: #24292e;
}
.container a.fcb {
  background-color: #4267B2;
}

.container a i {
  color: #fff;
}
</style>
