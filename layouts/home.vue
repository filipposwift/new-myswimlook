<template>
  <div class="layout__home">
    <nav class="left__navigation">
      <ul>
        <li class="nav__items">
          <nuxt-link :to="localePath('/styles/')">
            <span>Styles</span>
          </nuxt-link>
        </li>
        <li class="nav__items second">
          <nuxt-link :to="localePath('/designers/')">
            <span>Designers</span>
          </nuxt-link>
        </li>
      </ul>
      <!-- <div class="spacer"></div> -->
    </nav>
    <nav class="right__navigation">
      <ul>
        <li class="nav__items">
          <nuxt-link :to="localePath('/stories/')">
            <span>Stories</span>
          </nuxt-link>
        </li>
        <li class="nav__items second">
          <nuxt-link :to="localePath('/people/')">
            <span>People</span>
          </nuxt-link>
        </li>
      </ul>
      <!-- <div class="spacer"></div> -->
    </nav>
    <main class="main__container">
      <TheAppHeader />
      <nuxt class="main__content" />
      <TheAppFooter />
    </main>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.layout__home {
  display: grid;
  grid-template-columns: 4vw repeat(10, 1fr) 4vw;
  grid-auto-rows: 1fr;
  grid-column-gap: 0px;
  // overflow: hidden;
}

.spacer {
  height: calc(100vh - 55rem);
  background-color: get-color(primary, normal);
  overflow: hidden;
  border-top: 1px solid $b-color;
  border-bottom: 1px solid $b-color;
}

.main__container {
  grid-area: 1/2/2/12;
  overflow: hidden;
  width: 100%;
}

.left__navigation {
  grid-area: 1/1/2/2;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  position: fixed;
  top: 50px;
  width: 4vw;
  background-color: get-color(primary, normal);
  z-index: 10;
  border-left: 1px solid $b-color;

  a.nuxt-link-active {
    color: get-color(basic, normal);
  }
  @include phone {
    display: none;
  }
}

.nav__items {
  text-transform: uppercase;
  position: relative;
  @extend %paragraph-menu;
  height: 200px;
  // width: 100%;
  overflow: hidden;
  border-top: 1px solid $b-color;
  border-bottom: 1px solid $b-color;

  @include phone {
    display: none;
  }
  span {
    @extend %vertical-titles;
    display: block;
    padding: 0px 20px 0px 20px;
    transition: all 0.3s ease-in-out;
    cursor: pointer;
    &:hover {
      color: get-color(basic, normal);
    }
  }
  &.second {
    border-top: 0;
  }
}

.main__content {
  margin-top: 50px;
  width: 99.97%;
  overflow: hidden;
  border-left: 1px solid $b-color;
  border-right: 1px solid $b-color;
  @include phone {
    margin-top: 50px;
  }
}

.right__navigation {
  grid-area: 1/12/2/13;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  position: fixed;
  width: 4vw;
  top: 50px;
  right: 0;
  background-color: get-color(primary, normal);
  z-index: 10;
  // border-right: 1px solid $b-color;

  a.nuxt-link-active {
    color: get-color(basic, normal);
  }

  @include phone {
    display: none;
  }
}
</style>
