<template>
  <div id="left_panel" ref="leftPanel">
    <div class="left_panel_content">
      <secondaryNav />
    </div>
  </div>
</template>

<script>
import secondaryNav from './secondaryNav.vue'
export default {
  name: 'left_dashboard',
  components: {
    secondaryNav,
  },
  data() {
    return {
      BORDER_SIZE: 4,
      m_pos: null,
    }
  },
  mounted() {
    const panel = this.$refs.leftPanel
    panel.style.width = '30vw'
    panel.style.paddingRight = '4px'
    panel.style.height = '100%'
    panel.style.left = '0'
    panel.style.backgroundColor = '#18181b'
    const panelResize = this.resize.bind(this)
    panel.addEventListener('mousedown', this.startResize(panelResize), false)
    document.addEventListener('mouseup', this.stopResize(panelResize), false)
  },
  methods: {
    startResize(panelResize) {
      return function (e) {
        const panel = this.$refs.leftPanel
        if (e.offsetX > panel.offsetWidth - this.BORDER_SIZE) {
          this.m_pos = e.x
          document.addEventListener('mousemove', panelResize, false)
        }
      }.bind(this)
    },
    stopResize(panelResize) {
      return function () {
        document.removeEventListener('mousemove', panelResize, false)
      }
    },
    resize(e) {
      const dx = this.m_pos - e.x
      this.m_pos = e.x
      const panel = this.$refs.leftPanel
      panel.style.width =
        parseInt(getComputedStyle(panel, '').width) - dx + 'px'
    },
  },
}
</script>

<style>
#left_panel {
  position: fixed;
}

#left_panel::after {
  content: '';
  background-color: #3f3e47;
  position: absolute;
  right: 0;
  width: 5px;
  height: 100%;
  cursor: col-resize;
}
#left_panel::after:hover {
  background-color: #6944d3;
  width: 10px;
}
.left_panel_content {
  margin: 0;
  z-index: 1000;
  position: fixed;
}
</style>
