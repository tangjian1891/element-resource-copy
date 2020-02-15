
<script>
export default {
  name: "TjCol",
  data() {
    return {
      allResponse: []
    };
  },
  render(createElement) {
    return createElement(
      this.tag,
      {
        style: [this.calcColGutter],
        class: [
          "tj-col",
          "tj-col-" + this.span,
          "tj-col-offset-" + this.offset,
          this.calcResponse,
          this.calcPush,
          this.calcPull
        ]
      },
      this.$slots.default
    );
  },
  props: {
    span: {
      type: Number,
      default: 24
    },
    offset: {
      type: Number,
      default: 0
    },
    xs: {
      type: Number || Object,
      default: 0
    },
    sm: {
      type: Number || Object,
      default: 0
    },
    md: {
      type: Number || Object,
      default: 0
    },
    lg: {
      type: Number || Object,
      default: 0
    },
    xl: {
      type: Number || Object,
      default: 0
    },
    push: {
      type: Number,
      validator: function(newVal) {
        return newVal >= 0;
      }
    },
    pull: {
      type: Number,
      validator: function(newVal) {
        return newVal >= 0;
      }
    },
    tag: {
      type: String,
      default: "div"
    }
  },

  computed: {
    calcPush() {
      if (typeof this.push === "number") {
        return "tj-col-push-" + this.push;
      }
      return "";
    },
    calcPull() {
      if (typeof this.pull === "number") {
        return "tj-col-push-" + this.pull;
      }
      return "";
    },
    // 计算对应的class
    calcResponse() {
      let allResponse = [];
      if (typeof this.xs === "number" && this.xs !== 0) {
        allResponse.push("tj-col-xs-" + this.xs);
      }
      if (typeof this.sm === "number" && this.sm !== 0) {
        allResponse.push("tj-col-sm-" + this.sm);
      }
      if (typeof this.md === "number" && this.md !== 0) {
        allResponse.push("tj-col-md-" + this.md);
      }
      if (typeof this.lg === "number" && this.lg !== 0) {
        allResponse.push("tj-col-lg-" + this.lg);
      }
      if (typeof this.xl === "number" && this.xl !== 0) {
        allResponse.push("tj-col-md-" + this.xl);
      }
      return allResponse;
    },
    // 每个col左右padding
    calcColGutter() {
      if (this.$parent.gutter !== 0) {
        let value = +(this.$parent.gutter / 2) + "px";
        return {
          paddingLeft: value,
          paddingRight: value
        };
      }
      return "";
    },
    // 开始偏移
    calcColOffset() {
      // 偏移百分比。如果这个元素是第一个col，则取消左padding为0
      if (this.offset === 0) {
        return;
      }
      let value = (100 / 24) * this.offset + "%";
      return {
        marginLeft: value
      };
    }
  }
};
</script>

<style lang="scss">
.tj-col {
  // display: inline-block;
  float: left;
  box-sizing: border-box;
}

@for $item from 1 through 24 {
  .tj-col-#{$item} {
    width: 100%/24 * $item;
  }
  .tj-col-offset-#{$item} {
    margin-left: 100%/24 * $item;
  }
  .tj-col-push-#{$item} {
    left: 100%/24 * $item;
    position: relative;
  }
  .tj-col-pull-#{$item} {
    right: 100%/24 * $item;
    position: relative;
  }
}
@media only screen and (max-width: 767px) {
  @for $item from 1 through 24 {
    .tj-col-xs-#{$item} {
      width: 100%/24 * $item;
    }
  }
}
@media only screen and (min-width: 768px) {
  @for $item from 1 through 24 {
    .tj-col-sm-#{$item} {
      width: 100%/24 * $item;
    }
  }
}
@media only screen and (min-width: 992px) {
  @for $item from 1 through 24 {
    .tj-col-md-#{$item} {
      width: 100%/24 * $item;
    }
  }
}
@media only screen and (min-width: 1200px) {
  @for $item from 1 through 24 {
    .tj-col-lg-#{$item} {
      width: 100%/24 * $item;
    }
  }
}
@media only screen and (min-width: 1920px) {
  @for $item from 1 through 24 {
    .tj-col-xl-#{$item} {
      width: 100%/24 * $item;
    }
  }
}
</style>
