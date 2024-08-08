<template>
  <div>
    <div class="toolbar" v-if="toolBar">
      <div @click="$router.push('/')">Ho</div>
      <div @click="toggleToolDiv">Aa</div>
      <div @click="editTag = !editTag">md</div>
    </div>

    <div v-if="toolDiv" class="toolDiv">
      <div class="fontFamily">
        <div
          @click="updateFont(1)"
          style="
            font-family: 'Helvetica', Arial, sans-serif;
            background-color: #efeff2;
          "
        >
          Aa
        </div>
        <div
          @click="updateFont(2)"
          style="
            font-family: 'Georgia', Times New Roman, serif;
            background-color: #b2cff6;
          "
        >
          Aa
        </div>
      </div>
      <div class="grid">
        <div @click="updateCollumn(1)">single</div>
        <div @click="updateCollumn(2)">double</div>
      </div>
      <div class="option">
        <span @click="decreFontSize()">
          <svg viewBox="0 0 1024 1024" width="36" height="36">
            <path
              d="M128 503.467c0-17.067 17.067-34.134 34.133-34.134h699.734c17.066 0 34.133 17.067 34.133 34.134S878.933 537.6 861.867 537.6H162.133c-17.066 0-34.133-17.067-34.133-34.133z"
              fill="#333333"
            ></path>
          </svg>
        </span>
        <div>{{ styles.fontSize }}</div>
        <span @click="increFontSize()">
          <svg viewBox="0 0 1024 1024" width="36" height="36">
            <path
              d="M861.867 469.333H537.6v-307.2c0-17.066-17.067-34.133-34.133-34.133s-34.134 17.067-34.134 34.133v307.2h-307.2c-17.066 0-34.133 17.067-34.133 34.134s17.067 34.133 34.133 34.133h307.2v324.267c0 17.066 17.067 34.133 34.134 34.133s34.133-17.067 34.133-34.133V537.6h324.267c17.066 0 34.133-17.067 34.133-34.133s-17.067-34.134-34.133-34.134z"
              fill="#333333"
            ></path>
          </svg>
        </span>
      </div>
      <div class="option">
        <span @click="decreLineHeight()">
          <svg viewBox="0 0 1024 1024" width="36" height="36">
            <path
              d="M434.595 241.074h497.61c13.734 0 24.881-11.147 24.881-24.881s-11.147-24.88-24.88-24.88h-497.61c-13.735 0-24.882 11.145-24.882 24.88 0 13.734 11.147 24.88 24.881 24.88zM267.796 693.175h-0.1l-57.025-57.025v201.425H160.91V636.15l-57.026 57.025c-9.703 9.703-25.477 9.703-35.181 0-9.703-9.703-9.703-25.478 0-35.18l99.521-99.523c4.876-4.876 11.246-7.264 17.616-7.264a24.991 24.991 0 0 1 17.615 7.264l99.521 99.522c9.703 9.703 9.703 25.478 0 35.181-9.7 9.703-25.476 9.703-35.179 0zM103.883 335.177l57.026 57.026V190.678h49.761v201.525l57.026-57.026c4.876-4.876 11.246-7.266 17.615-7.266a24.99 24.99 0 0 1 17.615 7.266c9.703 9.703 9.703 25.478 0 35.181l-99.521 99.523c-9.703 9.703-25.479 9.703-35.182 0l-99.521-99.523c-9.703-9.703-9.703-25.478 0-35.181 9.704-9.703 25.477-9.703 35.181 0z m828.323 453.268h-497.61c-13.735 0-24.882 11.147-24.882 24.88s11.147 24.881 24.881 24.881h497.61c13.734 0 24.881-11.146 24.881-24.88s-11.146-24.88-24.88-24.88z m0-398.088h-497.61c-13.735 0-24.882 11.146-24.882 24.88s11.147 24.88 24.881 24.88h497.61c13.734 0 24.881-11.146 24.881-24.88s-11.146-24.88-24.88-24.88z m0 199.044h-497.61c-13.735 0-24.882 11.147-24.882 24.88s11.147 24.881 24.881 24.881h497.61c13.734 0 24.881-11.147 24.881-24.88S945.94 589.4 932.206 589.4z"
              fill="#333333"
            ></path>
          </svg>
        </span>
        <div>{{ styles.lineHeight }}</div>
        <span @click="increLineHeight()">
          <svg viewBox="0 0 1024 1024" width="36" height="36">
            <path
              d="M214.157992 820.759311l96.835378-96.843892c9.444654-9.43614 9.444654-24.7872 0-34.229422-9.441005-9.444654-24.7872-9.444654-34.233071 0l-55.489321 55.484455v-195.996341H172.852073v195.996341l-55.485671-55.484455h-0.099738c-9.439789-9.444654-24.790849-9.444654-34.231854 0-9.441005 9.442222-9.441005 24.793282 0 34.234287l96.839026 96.839027a24.293378 24.293378 0 0 0 12.788293 6.656869 251.382276 251.382276 0 0 1 17.384732-3.375263 24.042818 24.042818 0 0 0 4.111131-3.281606z"
              fill="#333333"
            ></path>
            <path
              d="M183.983751 552.551806a252.833335 252.833335 0 0 0 17.384732-3.375263 24.283648 24.283648 0 0 0-4.35561-0.40868 24.220399 24.220399 0 0 0-13.029122 3.783943zM100.173847 343.178477c6.194672 0 12.395425-2.328019 17.14147-7.069199l55.48932-55.489321v196.091214h48.420122V280.619957l55.48932 55.489321c9.441005 9.439789 24.7872 9.439789 34.233071 0 9.439789-9.445871 9.439789-24.792065 0-34.233071l-96.840243-96.843892c-9.439789-9.441005-24.790849-9.441005-34.23672 0l-96.834161 96.843892c-9.445871 9.441005-9.445871 24.7872 0 34.233071a24.295811 24.295811 0 0 0 17.137821 7.069199zM439.064828 246.988961h484.20243c13.362392 0 24.204587-10.847061 24.204587-24.211886 0-13.361175-10.842196-24.208236-24.204587-24.208236H439.064828c-13.359959 0-24.20702 10.847061-24.20702 24.208236 0 13.364824 10.847061 24.211885 24.20702 24.211886zM923.267258 779.60908H439.064828c-13.359959 0-24.20702 10.847061-24.20702 24.208236 0 13.363608 10.847061 24.210669 24.20702 24.210669h484.20243c13.362392 0 24.204587-10.847061 24.204587-24.210669 0-13.361175-10.842196-24.208236-24.204587-24.208236zM923.267258 585.926161H439.064828c-13.359959 0-24.20702 10.847061-24.20702 24.211886 0 13.361175 10.847061 24.213101 24.20702 24.213101h484.20243c13.362392 0 24.204587-10.847061 24.204587-24.213101 0-13.359959-10.842196-24.211885-24.204587-24.211886zM923.267258 392.248108H439.064828c-13.359959 0-24.20702 10.847061-24.20702 24.211886 0 13.359959 10.847061 24.20702 24.20702 24.20702h484.20243c13.362392 0 24.204587-10.847061 24.204587-24.20702 0-13.364824-10.842196-24.211885-24.204587-24.211886z"
              fill="#333333"
            ></path>
          </svg>
        </span>
      </div>
      <div class="theme-option">
        <div
          :style="{ backgroundColor: '#f1f1f1', color: '#333' }"
          @click="toggleTheme(1)"
        >
          正常
        </div>
        <div
          :style="{ backgroundColor: '#222', color: '#e9e9e9' }"
          @click="toggleTheme(2)"
        >
          黑夜
        </div>
        <div
          :style="{ backgroundColor: '#e0d7c5', color: '#5b4636' }"
          @click="toggleTheme(3)"
        >
          纸墨
        </div>
        <div
          :style="{ backgroundColor: '#CCE8CF', color: '#3D3D3D' }"
          @click="toggleTheme(4)"
        >
          护眼
        </div>
      </div>
    </div>

    <Editor v-if="editTag"></Editor>
  </div>
</template> 

<script>
export default {
  props: {
    styles: {
      type: Object,
    },
  },
  data() {
    return {
      toolBar: true,
      toolDiv: false,
      lastScrollTop: 0,
      editTag: false,
    };
  },
  watch: {
    styles: {
      handler(newStyles) {
        this.$emit("update:styles", newStyles);
        if (process.client) {
          localStorage.setItem("styles", JSON.stringify(newStyles));
        }
      },
      deep: true,
    },
  },
  mounted() {
    const savedStyles = JSON.parse(localStorage.getItem("styles"));
    if (savedStyles) {
      document.body.style.backgroundColor = savedStyles.backgroundColor;
      this.$emit("update:styles", savedStyles);
    } else document.body.style.backgroundColor = "#222";
    document.addEventListener("click", this.handleOutsideClick);
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
    document.removeEventListener("click", this.handleOutsideClick);
  },
  methods: {
    handleScroll() {
      const currentScrollTop =
        window.scrollY || document.documentElement.scrollTop;

      if (currentScrollTop > this.lastScrollTop) {
        this.toolBar = false;
        this.toolDiv = false;
      } else {
        this.toolBar = true;
      }

      this.lastScrollTop = currentScrollTop <= 0 ? 0 : currentScrollTop;
    },
    toggleToolDiv(event) {
      this.toolDiv = !this.toolDiv;
      event.stopPropagation();
    },
    handleOutsideClick(event) {
      const toolDivElement = this.$el.querySelector(".toolDiv");
      if (this.toolDiv && !toolDivElement.contains(event.target)) {
        this.toolDiv = false;
      }
    },
    increFontSize() {
      if (this.styles.fontSize < 10) this.styles.fontSize++;
    },
    decreFontSize() {
      if (this.styles.fontSize > 0) this.styles.fontSize--;
    },
    increLineHeight() {
      console.log(this.styles.lineHeight);
      if (this.styles.lineHeight < 10) this.styles.lineHeight++;
    },
    decreLineHeight() {
      if (this.styles.lineHeight > 0) this.styles.lineHeight--;
    },
    toggleTheme(index) {
      if (index === 1) {
        this.styles.backgroundColor = "#f1f1f1";
        this.styles.color = "#333";
      }
      if (index === 2) {
        this.styles.backgroundColor = "#222";
        this.styles.color = "#e9e9e9";
      }
      if (index === 3) {
        this.styles.backgroundColor = "#e0d7c5";
        this.styles.color = "#5b4636";
      }
      if (index === 4) {
        this.styles.backgroundColor = "#CCE8CF";
        this.styles.color = "#3D3D3D";
      }
      this.styles.theme = index;

      document.body.style.backgroundColor = this.styles.backgroundColor;
    },
    updateFont(index) {
      if (index === 1) this.styles.fontFamily = "Helvetica, Arial, sans-serif";
      else this.styles.fontFamily = "Georgia, Times New Roman, serif";
    },
    updateCollumn(index) {
      this.styles.gridTemplateColumns = `repeat(${index}, 1fr)`;
    },
  },
};
</script>

<style scoped>
.toolbar > div:hover {
  background-color: #4893f5;
}
.toolDiv {
  position: fixed;
  left: 45%;
  bottom: 0;
  width: 220px;
  height: 250px;
  color: #333;
  background: #f1f1f1;
  box-shadow: 0 0 8px 2px;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
.theme-option {
  display: flex;
  justify-content: space-evenly;
}
.theme-option > div {
  width: 50px;
  height: 40px;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
}
.fontFamily {
  display: flex;
  justify-content: space-evenly;
}
.fontFamily > div {
  cursor: pointer;
  box-shadow: 0 0 0 1px;
  width: 80px;
  height: 64px;
  line-height: 1.3;
  font-size: 48px;
  color: #5b4636;
}

.grid {
  display: flex;
  gap: 8px;
  justify-content: space-evenly;
}
.grid > div {
  cursor: pointer;
  width: 80px;
  font-size: 24px;
}
.grid > div:hover {
  background-color: #cab6b6;
}

.option {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
.option > span {
  height: 40px;
  width: 100%;
}
.option > span > :hover {
  background: #cab6b6;
}
</style>
