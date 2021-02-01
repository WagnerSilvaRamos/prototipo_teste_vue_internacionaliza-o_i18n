<template>
  <div id="app">
    <h1>{{ $t("welcomeMsg") }}</h1>
    <div class="list-languages">
      <button
        v-for="entry in languages"
        :key="entry.title"
        @click="changeLocale(entry.language)"
      >
        <flag :iso="entry.flag" v-bind:squared="false" /> {{ entry.title }}
      </button>
    </div>

    <HelloWorld msg="Welcome to  internationalization Prototype " />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import i18n from "@/plugins/i18n";

export default {
  name: "app",
  components: {
    HelloWorld,
  },
  data() {
    return {
      languages: [
        { flag: "us", language: "en", title: "English" },
        { flag: "br", language: "br", title: "Brasil" },
        { flag: "es", language: "es", title: "Español" },
        { flag: "de", language: "de", title: "Deustch" },
      ],
    };
  },
  methods: {
    changeLocale(locale) {
      i18n.locale = locale;
    },

    imageBg() {
      setInterval(function () {
        var $body = $("body");
        if ($body.hasClass("background1")) {
          $body.removeClass("background1");
          $body.addClass("background2");
        } else if ($body.hasClass("background2")) {
          $body.removeClass("background1");
          $body.removeClass("background2");
          $body.removeClass("background4");
          $body.addClass("background3");
        } else if ($body.hasClass("background3")) {
          $body.removeClass("background3");
          $body.removeClass("background2");
          $body.removeClass("background1");
          $body.addClass("background4");
        } else {
          $body.removeClass("background2");
          $body.addClass("background1");
          $body.removeClass("background3");
          $body.removeClass("background4");
        }
      }, 8000);
    },
  },

  created() {
    this.imageBg();
  },
};
</script>

<style>
body {
  font-size: 1em;
  font-family: Avenir, "Helvetica", Arial, sans-serif;
}

body {
  transition: background 0.5s linear;
  background-position: center;
  background-size: cover;
  background-image: url("assets/space.jpg");
}

body.background1 {
  background-image: url("assets/space.jpg");
}

body.background2 {
  background-image: url("assets/space_dois.jpg");
}

body.background3 {
  background-image: url("assets/space_tres.jpg");
}

body.background4 {
  background-image: url("assets/space_quatro.jpg");
}

#changeImage {
  /*background: url("assets/space.jpg") no-repeat center top;*/
  background-size: cover;
  max-width: 1920px;
  height: 1080px;
  width: 100%;
  display: block;
  margin: 0;
  padding: 0;
}

.list-languages {
  display: flex;
  margin: 0 auto;
  justify-content: center;
  max-width: 600px;
  flex-wrap: wrap;
}

#app {
  font-family: Avenir, "Helvetica", Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  padding: 15px;
  border: 1px solid green;
  margin: 10px;
  border-radius: 8px;
  font-size: 1.1em;
  cursor: pointer;
  max-width: 130px;
}

button {
  outline-color: #e181ec;
  outline-width: 3px;
}
.container {
  margin: 50px auto;
  max-width: 1120px;
  padding: 15px;
  background: #f2f2f2;
  border-radius: 8px;
  opacity: 0.8;
}

h1 {
  font-family: Arial, "Helvetica", sans-serif;
  font-size: 2em;
  color: #fff;
  margin: 0 auto 20px auto;
  text-shadow: #333 1px 1px 1px;
}
h2 {
  margin: 10px auto;
  color: #e4bf68;
  text-align: center;
  font-size: 1.5em;
  text-shadow: #333 1px 1px 1px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
p {
  max-width: 90%;
  line-height: 1.4em;
  margin: 0 auto;
}
</style>
