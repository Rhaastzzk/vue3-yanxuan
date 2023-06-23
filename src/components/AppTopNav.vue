<template>
  <div class="app-top-nav">
    <div class="w">
      <ul>
        <template v-if="userinfo.token">
          <li>
            <a href="javascript:;">张子康</a>
          </li>
          <li>
            <a href="javascript:;">退出登录</a>
          </li>
        </template>
        <li v-else>
          <a href="javascript:;">登录/注册</a>
        </li>
        <li>
          <a href="javascript:;">我的订单</a>
        </li>
        <li>
          <a href="javascript:;">会员</a>
          <ul class="dropdown">
            <li>
              <a href="javascript:;">开通</a>
            </li>
            <li>
              <a href="javascript:;">续费</a>
            </li>
          </ul>
        </li>
        <li>
          <a href="javascript:;">甄选家</a>
        </li>
        <li>
          <a href="javascript:;">客户服务</a>
        </li>
        <li>
          <a href="javascript:;">
            <i class="iconfont icon-phone"></i>
            APP
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { useStore } from "vuex";
import { computed } from "vue";
export default {
  setup(props) {
    const store = useStore();
    let userinfo = computed(() => {
      return store.state.user.userinfo;
    });

    return { userinfo };
  }
};
</script>

<style lang="less" scoped>
.app-top-nav {
  background-color: #333;

  ul {
    display: flex;
    height: 40px;
    line-height: 20px;
    justify-content: flex-end;

    li {
      position: relative;
      /* 添加相对定位，使下拉列表定位生效 */

      a {
        font-size: 12px;
        padding: 0 15px;
        color: #ccc;
        border-left: 1px solid #ccc;

        &:hover {
          color: @xtxColor;
        }
      }

      /* 下拉列表样式 */
      .dropdown {
        position: absolute;
        top: 100%;
        left: 0;
        display: none;

        li {
          a {
            display: block;
            padding: 5px 0;
            color: #f4ecec;
            border-left: none;
            background-color: #817e7edc;
            padding-left: 15px;
            width: 40px;
            height: 25px;

            &:hover {
              color: @xtxColor;
            }
          }
        }
      }

      &:hover .dropdown {
        display: block;
        /* 鼠标悬停时显示下拉列表 */
      }
    }

    li:nth-child(1) {
      a {
        border-left: 0;
      }
    }
  }
}
</style>







