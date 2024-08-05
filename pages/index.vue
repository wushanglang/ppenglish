<template>
  <div>
    <Aa
      v-if="$route.fullPath !== '/'"
      :styles.sync="styles"
      :style="{ backgroundColor: styles.color, color: styles.backgroundColor }"
      class="toolbar-container"
    ></Aa>
    <div class="article">
      <nuxt-child
        :style="computedStyles"
        :gridTemplateColumns="styles.gridTemplateColumns"
      ></nuxt-child>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      styles: {
        fontSize: 4,
        lineHeight: 3,
        color: "#f1f1f1",
        backgroundColor: "#222",
        fontFamily: "Georgia, Times New Roman, serif",
        gridTemplateColumns: `repeat(2, 1fr)`,
      },
      lastScrollTop: 0,
    };
  },
  computed: {
    computedStyles() {
      if (this.$route.fullPath === "/") return null;
      return {
        fontSize: this.styles.fontSize * 2 + 16 + "px",
        lineHeight: this.styles.lineHeight * 0.2 + 1.0,
        backgroundColor: this.styles.backgroundColor,
        color: this.styles.color,
        fontFamily: this.styles.fontFamily,
        gridTemplateColumns: this.styles.gridTemplateColumns,
      };
    },
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const currentScrollTop =
        window.scrollY || document.documentElement.scrollTop;
      const toolbar = this.$el.querySelector(".toolbar-container");

      if (currentScrollTop > this.lastScrollTop) {
        toolbar.style.visibility = "hidden";
      } else {
        toolbar.style.visibility = "visible";
      }

      this.lastScrollTop = currentScrollTop <= 0 ? 0 : currentScrollTop;
    },
  },
};
</script>

<style scoped>
.toolbar-container {
  text-align: center;
  user-select: none;
  width: 3rem;
  font-size: 16px;
  position: fixed;
  top: 45%;
  right: 0;
  margin-left: auto;
  padding: 0.2rem;
  transform-origin: top right;
  box-shadow: 0 0 2px 1px;
  border-radius: 0.125rem;
}
</style>
