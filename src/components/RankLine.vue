<template>
  <div class="rank-line-container" :style="containerStyle">
    <div class="rank-indicater" :style="indicaterStyle">
      {{ rank.name }}
    </div>
    <div class="rank-right" :style="rightStyle">
      <div
        class="rank-chara"
        v-for="chara in rank.charas"
        :key="chara.id"
        :style="charaStyle"
      >
        <img :src="charaIconSrc(chara.id)" />
      </div>
    </div>
  </div>
</template>

<script>
const charaIconSrc = function(id) {
  return `https://kirafanautodec.bitbucket.io/static/assets/texture/charauiresource/mergedcharaicon/charaicon_${id}.jpeg`;
};
export default {
  name: "RankLine",
  props: {
    rank: Object
  },
  data() {
    return {
      maxSlotEveryLine: 6,
      widthEverySlot: 128,
      heightEverySlot: 128,
      widthIndicator: 128,
      charaIconSrc: charaIconSrc
    };
  },
  computed: {
    slotNum: function() {
      return this.rank.charas.length;
    },
    lineNum: function() {
      return Math.ceil(this.slotNum / this.maxSlotEveryLine);
    },
    slotEveryLine: function() {
      return Math.min(this.maxSlotEveryLine, this.slotNum);
    },
    containerStyle: function() {
      return (
        `width: ${this.widthIndicator +
          this.slotEveryLine * this.widthEverySlot}px !important;` +
        `height: ${this.lineNum * this.heightEverySlot}px !important;`
      );
    },
    indicaterStyle: function() {
      return (
        `width: ${this.widthIndicator}px !important;` +
        `height: ${this.lineNum * this.heightEverySlot}px !important;`
      );
    },
    rightStyle: function() {
      return (
        `width: ${this.slotEveryLine * this.widthEverySlot}px !important;` +
        `height: ${this.lineNum * this.heightEverySlot}px !important;`
      );
    },
    charaStyle: function() {
      return (
        `width: ${this.widthEverySlot}px !important;` +
        `height: ${this.heightEverySlot}px !important;`
      );
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
div {
  display: flex;
  flex-wrap: wrap;
}

.rank-chara,
.rank-indicater {
  outline: 4px solid #000;
  outline-offset: -2px;
}
</style>
