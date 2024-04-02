<template>
  <div class="v-mining">
    <section class="v-header-section">
      <SpotAInternal 
      title="How to mine PKT"
      text="The PKT Network is powered by miners who run PacketCrypt, the world’s first and only bandwidth-hard, proof of work, mining algorithm. PacketCrypt economically incentivizes miners to collaborate, operate and grow the fully decentralized PKT Network. Mining has never been easier. Get started today." 
      button_1="Get a Mining Wallet" 
      button_2="Download Minr"
      button_3="Read Docs"
      button_1_link="/wallet"
      button_2_link="https://pkt.watch/minr/"
      button_3_link="https://docs.pkt.cash/"
      button_2_target="_blank"
      button_3_target="_blank" />
    </section>
    <!-- <section class="v-analytics-section">
      <AnalyticsData />
    </section> -->
    <section class="v-chess-section">
      <BlocksChessCommon :list="chess_list" />
    </section>
    <section class="v-block-links-section">
      <div class="container">
        <div class="v-block-links-section__inner">
          <div class="v-block-links-section__single dark_blue_bg">
            <div><h3 class="v-block-links-section__title">Start PKT mining</h3>
            <p class="v-block-links-section__descr">View PKT mining instructions, requirements, and FAQ related to using a PKT mining app. Or install PacketCrypt directly from Github.</p></div>
            <nuxt-link class="c-common-button c-common-button__bordered c-common-button__dark_blue" to="/setup">
              <span>Get started</span>
            </nuxt-link>
          </div>
          <div class="v-block-links-section__single green_bg">
            <div><h3 class="v-block-links-section__title">Blockchain Explorer</h3>
            <p class="v-block-links-section__descr">View PKT blocks, pools, transactions, addresses, balances, network steward wallet and more.</p></div>
            <a href="https://packetscan.io/" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>View explorer</span></a>
          </div>
        </div>
        <div class="v-block-links-section__inner">
          <div class="v-block-links-section__single orange_bg">
            <div><h3 class="v-block-links-section__title">Setup a PKT mining pool</h3>
            <p class="v-block-links-section__descr">PKT mining pools require technical operators with substantial bandwidth and processing infrastructure to validate blocks.</p></div>
            <a href="https://docs.pkt.cash/en/latest/mining/pool_setup_guide/" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Learn more</span></a>
          </div>
          <div class="v-block-links-section__single blue_bg">
            <div><h3 class="v-block-links-section__title">Install a PKT miner</h3>
            <p class="v-block-links-section__descr">Begin PKT mining using the PKT World wallet or with the Minr app for MacOS, Linux or Windows.</p></div>
            <a href="https://docs.pkt.cash/en/latest/mining/" target="_blank" class="c-common-button c-common-button__bordered c-common-button__dark_blue"><span>Read docs</span></a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import SpotAInternal from "~/components/Common/SpotAInternal";
// import AnalyticsData from "~/components/Mine/AnalyticsData";
import BlocksChessCommon from "~/components/Common/BlocksChessCommon";
export default {
  components: {
    SpotAInternal,
    // AnalyticsData,
    BlocksChessCommon
  },
  data() {
    return {
      chess_list: [
        {
          text_direction: "text_right",
          single_title: "Why Mine PKT?",
          single_subtitle: "Mining is the backbone of the PKT Network",
          single_descr: "Mining requires bandwidth and CPU power, which encrypts the network and establishes its high speed data infrastructure. When PKT Lightning Network launches, its near-infinite transactions per second and near-instantaneous settlement will make PKT one of the highest throughput blockchains in the world.",
          single_url: "/pkt-cash",
          external: false,
          single_link: "Learn more",
          single_img: "/img/mine/mine-1.webp",
        },
        {
          text_direction: "text_left",
          single_title: "How to Mine PacketCrypt?",
          single_subtitle: "Bandwidth + CPU",
          single_descr: "PacketCrypt can be easily mined from any CPU powered device. PKT mining pools are community powered and require significant bandwidth resources. Miners and PKT mining pools are incentivized to collaborate, which decentralizes the network infrastructure and propagates the network.",
          single_url: "https://docs.pkt.cash/en/latest/",
          external: true,
          single_link: "Read docs",
          single_img: "/img/mine/mine-2.webp",
        }
      ]
    };
  },
  head() {
    return {
      title: "Mine - PKT",
      meta: [{ hid: "description", name: "description", content: "The PKT Network is powered by miners who run PacketCrypt, the world’s first and only bandwidth-hard, proof of work, mining algorithm. PacketCrypt economically incentivizes miners to collaborate, operate and grow the fully decentralized PKT Network. Mining has never been easier. Get started today." }],
      link: [
        {
          rel: 'canonical',
          href: 'https://pkt.cash' + this.$route.path
        }
      ]
    };
  },
};
</script>
<style lang="scss">
.v-mining {
  background-color:$black_blue;
  position:relative;
  &:before {
    content:'';
    background-image:url(/img/mine/mine-bg.webp);
    position:absolute;
    bottom:0;
    right:0;
    width:80%;
    height:70%;
    background-position:left center;
    background-size:cover;
    background-repeat:no-repeat;
    z-index:1;
  }
  &:after {
    content:'';
    background-image:url(/img/mine-top-asset.webp);
    position:absolute;
    top:0;
    right:0;
    width:55%;
    height:55%;
    background-position:right top;
    background-size:contain;
    background-repeat:no-repeat;
    z-index:1;
    @include for-width(-desktop-medium) {
      width:60%;
      height:60%;
    }
    @include for-width(-small-lg) {
      width:100%;
      height:rem(800);
      background-size:cover;
      background-position:right -250px top -150px;
    }
  }
  & > section {
    z-index:3;
    position:relative;
  }
  .v-header-section {
    .c-spot-a-internal {
      @include for-width(-small-lg) {
        padding:rem(125) 0 rem(100);
      }
      &__title {
        max-width:rem(475);
        @include for-width(-small-lg) {
          max-width:rem(200);
        }
      }
      &__links {
        @include for-width(-small-lg) {
          margin-top:rem(35);
        }
        & .c-common-button {
          @include for-width(-small-lg) {
            width:47%;
          }
        }
        & .c-common-button__filled {
          @include for-width(-small-lg) {
            width:100%;
            margin-bottom:rem(20);
          }
        }
      }
    }
  }
  .v-chess-section {
    & .text_right {
      & .c-chess-block_inner_single_title {
        padding-right:rem(50);
        @include for-width(-small-lg) {
          padding-right:0;
        }
      }
    }
  }
  .v-block-links-section {
    padding:rem(150) 0;
    @include for-width(-small-lg) {
      padding:rem(110) 0 rem(80);
    }
    &__inner {
      @extend %df;
      @extend %jcsb;
      @extend %fw;
      padding-bottom:3%;
      &:last-child {
        padding-bottom:0;
      }
      @include for-width(-small-lg) {
        display:block;
        padding-bottom:0;
      }
    }
    &__single {
      width:48.5%;
      border-radius:rem(20);
      padding:rem(30) rem(40);
      @extend %df;
      @extend %jcsb;
      @extend %fdc;
      @extend %ais;
      @include for-width(-laptop) {
        padding:rem(25) rem(30);
      }
      @include for-width(-small-lg) {
        width:100%;
        padding:rem(20) rem(30);
        margin-bottom:rem(20);
      }
    }
    &__title {
      font-size: rem(40);
      line-height: rem(50);
      color:$black_blue;
      @extend %inter_semibold;
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
      padding:rem(12) 0 rem(65);
      @include for-width(-small-lg) {
        font-size: rem(16);
        line-height: rem(24);
      }
    }
  }
}
</style>