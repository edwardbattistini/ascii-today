<template>
 <div :class="'empty-state state-' + animationState">
          <div class="space"><br /></div>
          <br />
          ^<br />
          <div class="line">|<br /></div>
          |<br />
&nbsp;+---------+----------+<br />
&nbsp;| Just start typing! |<br />
&nbsp;+--------------------+<br />

        </div>
</template>

<script>

export default {
  name: 'empty-state',

  data() {
    return {
      animationState: 1
    }
  },

  mounted() {
    this.animationInterval = setInterval(() => {
      this.animationState = (this.animationState + 1) % 2;
    }, 600);
  },
  destroyed() {
    window.clearInterval(this.animationInterval);
  }
}

</script>

<style lang="sass" scoped>
.state-0 {
  .space {
    display: none;
  }
  .line {
    display: block;
  }
}

.state-1 {
  .space {
    display: block;
  }
  .line {
    display: none;
  }
}
</style>

