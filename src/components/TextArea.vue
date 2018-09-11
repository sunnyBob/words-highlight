<template>
  <div>
    <div ref="textarea" class="text_box" contenteditable="true" v-html="content">
    </div>
    <button @click="checkKeyWords">检测</button>
    <button @click="seeResult">查看敏感词</button>
  </div>
</template>

<script>
export default {
  name: 'TextArea',
  data() {
    return {
      content: `Welcome to my textarea highlight
        testWelcome textarea highlight testWelcome
        textarea highlight testWelcome to my textarea highlight
        testWelcome to my textarea highlight testWelcome to my textarea
        highlight testWelcome to my textarea highlight testdnfjkdskjbvdk
        svbkjdsvWelcome to my textarea highlight testWelcome my textarea high
        light testWelcome to my textarea highlight testWelcome my textarea highlight testWelcome
        to my textarea highlight testWelcome my textarea
        highlight test 斯卡哈事发地撒女的深V 阿萨德v但是是大部分大沙发大师傅大师傅 暗室逢灯答复不太认同不然不然brbk
        jkjkjbsdv  vevervnejkvnkjnernvkjrebvberjbvjkrbejkbvjrbekbvjkjshvoehvrbebvjxsdfjdsjhfgdsjfbvkje
        Welcome to my textarea highlight
        testWelcome textarea highlight testWelcome
        textarea highlight testWelcome to my textarea highlight
        testWelcome to my textotarea highlight testWelcome to my textarea
        highlight testWelcome to my textarea highlight testdnfjkdskjbvdk
        svbkjdsvWelcome to my textarea highlight testWelcome my textarea high
        light testWelcome to my textarea highlight testWelcome my textarea highlight testWelcome
        to my textarea highlight testWelcome my textareatestWelcome textarea highlight testWelcome
        textarea highlight testWelcome to my textarea highlight
        testWelcome to my textarea highlight testWelcome to my textarea
        highlight testWelcome to my textarea highlight testdnfjkdskjbvdk
        svbkjdsvWelcome to my textarea highlight testWelcome my textarea high
        light testWelcome to my textarea highlight testWelcome my textarea highlight testWelcome
        to my textarea highlight testWelcome my textarea
        highlight test 斯卡哈事发地撒女的深V 阿萨德v但是是大部分大沙发大师傅大师傅 暗室逢灯答复不太认同不然不然brbk
        jkjkjbsdv  vevervnejkvnkjnernvkjrebvberjbvjkrbejkbvjrbekbvjkjshvoehvrbebvjxsdfjdsjhfgdsjfbvkje
        Welcome to my textarea highlight
        testWelcome textarea highlight testWelcometestWelcome textarea highlight testWelcome
        textarea highlight testWelcome to my textarea highlight
        testWelcome to my tex关键字tarea highlight testWelcome to my textarea
        highlight testWelcome to my textarea highlight testdnfjkdskjbvdk
        svbkjdsvWelcome to my textarea highlight testWelcome my textarea high
        light testWelcome to my textarea highlight testWelcome my textarea highlight testWelcome
        to my textarea highlight testWelcome my textarea
        highlight test 斯卡哈事发地撒女的深V 阿萨德v但是是大部分大沙发大师傅大师傅 暗室逢灯答复不太认同不然不然brbk
        jkjkjbsdv  vevervnejkvnkjnernvkjrebvberjbvjkrbejkbvjrbekbvjkjshvoehvrbebvjxsdfjdsjhfgdsjfbvkje
        Welcome to my textarea highlightlight testWelcome to my textarea highlight testWelcome my textarea highlight testWelcome
        to my textarea highlight testWelcome my textarea
        highlight test 斯卡哈事发地撒女的深V 阿萨德v但是是大部分大沙发大师傅大师傅 暗室逢灯答复不太认同不然不然brbk
        jkjkjbsdv  vevervnejkvnkjnernvkjrebvberjbvjkrbejkbvjrbekbvjkjshvoehvrbebvjxsdfjdsjhfgdsjfbvkje
        Welcome to my textarea highlight
        testWelcome textarea highlight testWelcometestWelcome textarea highlight testWelcome
        textarea highlight testWelcom关键字e to my textarea highlightlight testWelcome to my textarea highlight testWelcome my textarea highlight testWelcome
        to my textarea highlight testWelcome my textarea
        highlight test 斯卡哈事发地撒女的深V 阿萨德v但是是大部分大沙发大师傅大师傅 暗室逢灯答复不太认同不然不然brbk
        jkjkjbsdv  vevervnejkvnkjnernvkjrebvberjbvjkrbejkbvjrbekbvjkjshvoehvrbebvjxsdfjdsjhfgdsjfbvkje
        Welcome to my textarea highlight
        testWelcome textarea highlight testWelcometestWelcome textarea highlight testWelcome
        textarea highlight testWelcome to my textarea highlight
        testWelcome textarea highlight testWelcome`,
      keywords: ['关键字'],
      i: 0,
    }
  },
  methods: {
    checkKeyWords() {
      const reg = new RegExp(this.keywords.join('|'), 'gi');
      this.content = this.content.replace(reg, word => `<span class="highlight">${word}</span>`);
    },
    seeResult() {
      const keySpans = document.querySelectorAll('span');
      if (keySpans.length) {
        const index = this.i++ % keySpans.length;
        this.$refs.textarea.scrollTop = keySpans[index].offsetTop;
      }
    }
  },
  updated() {
    const keySpan = document.querySelector('span');
    if (keySpan) {
      this.$refs.textarea.scrollTop = keySpan.offsetTop;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.text_box {
  text-align: left;
  width: 400px;
  min-height: 120px;
  max-height: 120px;
  margin-left: auto;
  margin-right: auto;
  padding: 3px;
  outline: 0;
  border: 1px solid #a0b3d6;
  font-size: 12px;
  word-wrap: break-word;
  overflow-x: hidden;
  overflow-y: auto;
  position: relative;
}
</style>
