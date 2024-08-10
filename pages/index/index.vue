 <template>
  <div class="con">
    <Nav class="nav"></Nav>
    <div v-for="article in data" :key="article.time">
      <div class="time">
        {{ article.time }}
      </div>
      <div class="group">
        <nuxt-link
          v-for="item in article.links"
          :key="item.to"
          class="article tooltip"
          :to="item.to"
          :class="{ active: $route.path.startsWith(item.to) }"
        >
          <span class="tooltiptext">{{ item.cn_title }}</span>
          <h3 class="title">{{ item.title }}</h3>
          <p class="subtitle">{{ item.subtitle }}</p>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [
        {
          time: "2024-08",
          links: [
            {
              to: "/2408/1",
              title: "Kamala Harris and the Legacy of Bidenomics",
              subtitle: "Kamala Harris and the Legacy of Bidenomics",
              cn_title: "卡玛拉·哈里斯与“拜登经济学”遗产",
            },
            {
              to: "/2408/2",
              title: "What Don’t We Know?",
              subtitle: "We have a lot to learn from studying our ignorance.",
              cn_title: "我们还都不知道什么？",
            },
            {
              to: "/2408/3",
              title: "“Wrong Way” Takes the Shine Off the Self-Driving Car",
              subtitle:
                "Joanne McNeil’s novel suggests that much of what we think of as technological progress is a new way to obscure human labor.",
              cn_title: "「反方向」让自动驾驶汽车光彩不再",
            },
            {
              to: "/2408/4",
              title: "Black Holes Are Even Weirder Than You Imagined",
              subtitle:
                "It’s now thought that they could illuminate fundamental questions in physics, settle questions about Einstein’s theories, and even help explain the universe.",
              cn_title: "黑洞比你想象的还要奇怪",
            },
          ],
        },
        {
          time: "2024-07",
          links: [
            {
              to: "/2407/1",
              title: "The Macabre Ironies of “Trap”",
              subtitle:
                "Lurking beneath M. Night Shyamalan’s new thriller are the commonplace horrors of family life.",
              cn_title: "“Trap”里的恐怖与讽刺",
            },
            {
              to: "/2407/2",
              title: "In the Age of A.I., What Makes People Unique?",
              subtitle:
                "More than ever, we’re challenged to define what’s valuable about being human.",
              cn_title: "在人工智能时代，是什么让人与众不同？",
            },
            {
              to: "/2407/3",
              title: "The Supreme Court Needs Fixing, but How?",
              subtitle:
                "Joanne McNeil’s novel suggests that much of what we think of as technological progress is a new way to obscure human labor.",
              cn_title: "最高法院需要修补，但如何修？",
            },
            {
              to: "/2407/4",
              title: "“Weird” Is a Rebuke to Republican Dominance Politics",
              subtitle:
                "The Democrats’ new favorite attack line has less to do with their opponents’ distance from the norm than with their desired level of control.",
              cn_title: "“Weird” 是对共和党主导政治的驳斥",
            },
          ],
        },
      ],
      darkTheme: false,
    };
  },
  mounted() {
    document.body.style.backgroundColor = "#fefefe";
  },
};
</script>

<style scoped>
.con {
  max-width: 65rem;
  margin: 0 auto;
}
.group {
  font-size: 16px;
  display: grid;
  gap: 10px;
  grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
}
@media (max-width: 700px) {
  .group {
    grid-template-columns: 1fr;
  }
}
a {
  color: #222;
  text-decoration: none;
}
.subtitle {
  text-decoration: none;
}
.time {
  margin-top: 1.2rem;
  text-align: center;
  color: #555;
  font-size: 1.2rem;
}
.article {
  height: 155px;
  min-width: 380px;
  background-color: #fafafa;
  padding: 8px 12px;
  border-radius: 4px;
  transition: box-shadow 150ms;
  box-shadow: 0.0145rem 0.029rem 0.174rem rgba(129, 145, 181, 0.01698),
    0.0335rem 0.067rem 0.402rem rgba(129, 145, 181, 0.024),
    0.0625rem 0.125rem 0.75rem rgba(129, 145, 181, 0.03),
    0.1125rem 0.225rem 1.35rem rgba(129, 145, 181, 0.036),
    0.2085rem 0.417rem 2.502rem rgba(129, 145, 181, 0.04302),
    0.5rem 1rem 6rem rgba(129, 145, 181, 0.06),
    0 0 0 0.0625rem rgba(129, 145, 181, 0.015);
}
.article:hover {
  box-shadow: 0.0145rem 0.029rem 0.174rem rgba(69, 77, 97, 0.05),
    0.0335rem 0.067rem 0.402rem rgba(69, 77, 97, 0.05),
    0.0625rem 0.125rem 0.75rem rgba(69, 77, 97, 0.05),
    0.1125rem 0.225rem 1.35rem rgba(69, 77, 97, 0.05),
    0.2085rem 0.417rem 2.502rem rgba(69, 77, 97, 0.05),
    0.5rem 1rem 6rem rgba(69, 77, 97, 0.05),
    0 0 0 0.0625rem rgba(69, 77, 97, 0.05);
}
</style> 

 