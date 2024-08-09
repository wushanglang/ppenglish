<template>
  <div class="con">
    <Nav class="nav"></Nav>
    <main>
      <h4>网站初衷</h4>
      <p>
        泡泡外刊旨在帮助广大英语爱好者更好的学习英语。文章摘自知名期刊，适合有四六级、考研等应试需求的读者进行<strong>长难句练习</strong>，提高语感。
      </p>

      <h4>特点</h4>
      <ul>
        <li>
          翻译由<a href="https://tongyi.aliyun.com/qianwen/" target="_blank"
            >qwen-plus</a
          >大模型以及<a href="https://ai.youdao.com/" target="_blank"
            >有道智云</a
          >提供，有效减少传统机翻的僵硬。
        </li>
        <li>主流外刊文章，适配四六级、考研等英语学习者需求。</li>
        <li>用户自定义布局，提高阅读体验。</li>
        <li>markdown笔记</li>
      </ul>

      <h4>反馈</h4>
      <p>
        网站开源且长期更新，希望得到您的帮助。如果您有好的想法、文章数据源或者发现错误，请到<a
          href="https://github.com/wushanglang/ppenglish"
          target="_blank"
          >github</a
        >上提交issue。
      </p>

      <h4>声明</h4>
      <p>
        本网站旨在为广大学习爱好者提供一个交流与学习的平台。如果文章内容侵犯了您的权益，请联系cww3309@gmail.com，在确认身份后下架相关内容。
      </p>

      <h4>其他</h4>
      <p>
        是否有桌面端的单词记忆需求呢？试试我做的<a
          href="https://github.com/wushanglang/hhword"
          target="_blank"
          >欢欢单词</a
        >吧。它基于A4纸背单词法构建，如果你会<strong>盲打</strong>的话会是不错的选择🥰🥰🥰
      </p>
    </main>
  </div>
</template>
 
<script>
export default {
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

.nav {
  margin: 0;
}
li {
  margin-left: 1rem;
  list-style: circle !important;
}
a {
  color: #6988e6;
}
h4 {
  margin: 1.4rem 0 0 0;
}
p {
  margin: 0;
}
</style>
