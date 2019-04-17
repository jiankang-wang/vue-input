<script>
export default {
  model: {
    prop: 'inputVal',
    event: 'changeValue'
  },
  props: {
    inputVal: {
      type: String,
      default: ''
    }
  },
  methods: {
    filter(val) {
      const reg = /^[1-9]\d*((\.)|(\.[1-9]{1}))?$/
      const s = reg.exec(val)
      let newVal = val

      const reg1 = /[\u4e00-\u9fa5A-Za-z]+/g
      const s2 = reg1.exec(newVal)
      if (s2) {
        newVal = newVal.replace(s2[0], '')
      } else {
        if (s) {
          newVal = s[0]
        } else {
          newVal = newVal.slice(0, -1)
        }
      }
      // this.inputVal = newVal
      this.$emit('changeValue', newVal)
      return newVal
    }
  },
  render() {
    return (<div>
      <el-input
        type="text"
        value={ this.inputVal }
        on-input = { this.filter }
        autocomplete="off">
      </el-input>
    </div>)
  }
}
</script>
