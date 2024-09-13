<template>
  <div class="v-devcenter">
    <section class="v-header-section">
      <SpotAInternal 
      title="Developer Central"
      text="PKT is a community project. All the technology in the ecosystem is developed by contributors and/or community member companies inspired by PKT’s mission. Here you will find all the documentation you need to begin building within the ecosystem." 
      button_1="Get funding"
      button_2="Read docs"
      button_1_link="/network-steward"
      button_2_link="https://docs.pkt.net/"
      button_2_target="_blank"  />
    </section>
    <section class="v-simple-section">
      <SimpleText :list="simple_block" />
    </section>
    <section class="v-block-links-section">
      <div class="container">
        <div class="v-block-links-section__inner">
          <div class="v-block-links-section__single orange_bg">
            <div><h3 class="v-block-links-section__title">Install a cjdns node</h3>
            <p class="v-block-links-section__descr">When you install cjdns you are adding core physical infrastructure to the VPN-based PKT Network.</p></div>
            <a href="https://github.com/cjdelisle/cjdns" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Install now</span></a>
          </div>
          <div class="v-block-links-section__single blue_bg">
            <div><h3 class="v-block-links-section__title">Begin mining PKT</h3>
            <p class="v-block-links-section__descr">Mining can be done from any computer. The PKT World wallet has a miner built-in, so it’s easy to participate.</p></div>
            <a href="https://pkt.world/mining" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Get started</span></a>
          </div>
          <div class="v-block-links-section__single green_bg">
            <div><h3 class="v-block-links-section__title">Setup a PKT mining pool</h3>
            <p class="v-block-links-section__descr">PKT mining pools require skilled operators with substantial bandwidth and bare metal infrastructure.</p></div>
            <a href="https://docs.pkt.net/en/latest/mining/pool_setup_guide/" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Read docs</span></a>
          </div>
        </div>
        <div class="v-block-links-section__inner">
          <div class="v-block-links-section__single dark_blue_bg">
            <div><h3 class="v-block-links-section__title">Run a PKT FullNode</h3>
            <p class="v-block-links-section__descr">Each PKT FullNode validates the blocks and helps the wallets to receive and send PKT.</p></div>
            <a href="https://docs.pkt.net/en/latest/pktd/" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Install now</span></a>
          </div>
          <div class="v-block-links-section__single grey_bg">
            <div><h3 class="v-block-links-section__title">PKT Lightning Network</h3>
            <p class="v-block-links-section__descr">PKT Lightning Network is designed to fortify the speed and portability of transactions across the PKT Network.</p></div>
            <a href="https://github.com/cjdelisle/PKT-Lightning-Wallet" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Learn More</span></a>
          </div>
          <div class="v-block-links-section__single rose_bg">
            <div><h3 class="v-block-links-section__title">Build a website in PKT Network</h3>
            <p class="v-block-links-section__descr">Get more information about building and hosting censorship-resistant websites in the PKT Network.</p></div>
            <a href="https://docs.pkt.net/en/latest/cjdns_websites/" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Learn more</span></a>
          </div>
        </div>
      </div>
    </section>
    <section class="v-join-section">
      <JoinCommunity />
    </section>
  </div>
</template>

<script>
import SpotAInternal from "~/components/Common/SpotAInternal";
import SimpleText from "~/components/Common/SimpleText";
import JoinCommunity from "~/components/Common/JoinCommunity";
export default {
  components: {
    SpotAInternal,
    SimpleText,
    JoinCommunity
  },
  data() {
    return {
      simple_block: [
        {
          single_title: "Get Started",
          single_text: "PKT is permissionless, so everyone is empowered to develop the project. Get started by either mining PacketCrypt or installing a cjdns node. These efforts are the infrastructure of the PKT Network. PKT Network supports censorship-resistant websites. These sites can be reached peer-to-peer within the PKT Network, or from the global internet using a reverse VPN. If funding is needed, check out the Network Steward, which is a grant mechanism to fund PKT-related projects.",
        }
      ]
    };
  },
  head() {
    return {
      title: "Developer Central - PKT",
      meta: [{ hid: "description", name: "description", content: "PKT is a community project. All the technology in the ecosystem is developed by contributors and/or community member companies inspired by PKT’s mission. Here you will find all the documentation you need to begin building within the ecosystem." }],
      link: [
        {
          rel: 'canonical',
          href: 'https://pkt.net' + this.$route.path
        }
      ]
    };
  },
};
</script>
<style lang="scss">
.v-devcenter {
  background-color:$black_blue;
  position:relative;
  background-image:url(/img/developer-center-top.webp);
  background-position:right top;
  background-size:rem(600);
  background-repeat:no-repeat;
  @include for-width(-desktop-med) {
    background-size:rem(550);
  }
  @include for-width(-desktop-med) {
    background-size:rem(550);
  }
  @include for-width(-tablet) {
    background-size:rem(450);
  }
  @include for-width(-small-lg) {
    background-size:100%;
    background-image:url(/img/developer-center-top-mobile.webp);
    background-position:right top;
  }
  &:before {
    content:'';
    background-image:url(/img/pkt-network-before.webp);
    position:absolute;
    top:5%;
    left:0;
    width:85%;
    height:85%;
    background-position:left top;
    background-size:contain;
    background-repeat:no-repeat;
    z-index:1;
    @include for-width(-small-lg) {
      background-size:cover;
      width:100%;
    }
  }
  &:after {
    content:'';
    background-image:url(/img/pkt-network-after.webp);
    position:absolute;
    bottom:0;
    right:0;
    width:65%;
    height:60%;
    background-position:right bottom 60%;
    background-size:cover;
    background-repeat:no-repeat;
    z-index:1;
    @include for-width(-small-lg) {
      display:none;
    }
  }
  & > section {
    z-index:3;
    position:relative;
  }
  & .c-spot-a-internal {
    @include for-width(-small-lg) {
      padding:rem(120) 0 rem(70);
    }
    &__title {
      max-width:rem(475);
      @include for-width(-small-lg) {
        max-width:rem(200);
      }
    }
  }
  .v-simple-section {
    .c-common-simple {
      & .container {
        padding: rem(54) rem(105) rem(60);
        @include for-width(-laptop) {
          padding: rem(35) rem(100) rem(40);
        }
        @include for-width(-tablet) {
          padding: rem(35) rem(50) rem(40);
        }
        @include for-width(-small-lg) {
          padding: rem(35) rem(25);
        }
      }
    }
  }
  .v-block-links-section {
    padding:rem(150) 0 rem(0);
    @include for-width(-tablet) {
      padding:rem(100) 0 0;
    }
    &__inner {
      @extend %df;
      @extend %jcsb;
      @extend %fw;
      padding-bottom:rem(60);
      &:last-child {
        padding-bottom:0;
      }
      @include for-width(-tablet) {
        display:block;
        padding-bottom:0;
      }
    }
    &__single {
      width:31.5%;
      border-radius:rem(20);
      padding:rem(20) rem(30) rem(40);
      @extend %df;
      @extend %jcsb;
      @extend %fdc;
      @extend %ais;
      @include for-width(-laptop) {
        padding:rem(25) rem(30);
      }
      @include for-width(-tablet) {
        width:100%;
        margin-bottom:rem(20);
      }
      @include for-width(-small-lg) {
        padding:rem(20) rem(30);
      }
    }
    &__title {
      font-size: rem(40);
      line-height: rem(50);
      color:$black_blue;
      @extend %inter_bold;
      @include for-width(-laptop) {
        font-size: rem(34);
        line-height: rem(44);
      }
      @include for-width(-small-lg) {
        font-size: rem(30);
        line-height: rem(36);
      }
    }
    &__descr {
      @extend %p-big-common;
      color:$black_blue;
      padding:rem(10) 0 rem(20);
      @include for-width(-small-lg) {
        font-size: rem(16);
        line-height: rem(24);
      }
    }
  }
}
</style>
