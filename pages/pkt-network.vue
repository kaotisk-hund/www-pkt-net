<template>
  <div class="v-network">
    <section class="v-header-section">
      <SpotAInternal 
      title="Scaling the PKT Network"
      text="PKT Network is a high speed, VPN-based network. The network’s decentralized physical infrastructure (DePIN) is designed to support open internet access and empower people to build websites where the web URL is also a PKT payment address." 
      button_1="Ecosystem"
      button_2="Roadmap"
      button_1_link="/ecosystem"
      button_2_link="/build" />
    </section>
    <!-- <section class="v-analytics-section">
      <AnalyticsDataNetwork />
    </section> -->
    <section class="v-simple-section">
      <SimpleText :list="simple_block" />
    </section>
    <section class="v-asymetrical-section">
      <div class="container">
        <div class="v-asymetrical-section__heading">
          <h2>PKT’s Integrated Payment Rails</h2>
        </div>
        <div class="v-asymetrical-section__inner">
          <BlockAsymmetrical :listFirst="asymetrical_block_list" :listSecond="asymetrical_block_list_second" />
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
// import AnalyticsDataNetwork from "~/components/Network/AnalyticsDataNetwork";
import SimpleText from "~/components/Common/SimpleText";
import BlockAsymmetrical from "~/components/Common/BlockAsymmetrical";
import JoinCommunity from "~/components/Common/JoinCommunity";
export default {
  components: {
    SpotAInternal,
    // AnalyticsDataNetwork,
    SimpleText,
    BlockAsymmetrical,
    JoinCommunity
  },
  data() {
    return {
      simple_block: [
        {
          single_title: "What is PKT Network?",
          single_text: "PKT Network is an decentralized ecosystem powered by the people. Contributors are earn PKT 	cryptocurrency by connecting bandwidth and computer processing resources to power the network. The result is a secure, high speed, permissionless, user-operated web infrastructure. Websites built in the PKT Network are censorship-resistant, yet reachable from any web browser using a reverse VPN and payments can be paid directly to a web URL within the network.",
        }
      ],
      asymetrical_block_list: [
        {
          single_title: "Peer-to-peer Payments",
          single_descr: "Link a cjdns IPv6 address to a PKT wallet address and seamlessly receive payments without a third party payment processor.",
          color: "blue_dot"
        },
        {
          single_title: "No Fees",
          single_descr: "Enjoy near-zero gas fees and no third party payment processor fees when using PKT’s payment rails.",
          color: "green_dot"
        }
      ],
      asymetrical_block_list_second: [
        {
          single_title: "Scalable",
          single_descr: "Upon PKT Lightning Network launch, PKT will have near-infinite transactions per second for unlimited scalability.",
          color: "green_dot"
        },
        {
          single_title: "Layer-2 Payment Rails",
          single_descr: "PKT Lighting Network  is a fork of Bitcoin’s layer-2 Lightning Network. Payments will soon process over PKT Lighting Network offering near-instant settlement.",
          color: "blue_dot"
        }
      ],
    };
  },
  head() {
    return {
      title: "Scaling the PKT Network - PKT",
      meta: [{ hid: "description", name: "description", content: "PKT Network is a high speed, peer-to-peer, VPN-based network. This decentralized infrastructure (DePIN) is expanding open internet access and powering the future of the decentralized web." }],
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
.v-network {
  background-color:$black_blue;
  position:relative;
  background-image:url(/img/pkt-network-before.webp);
  background-position:left center;
  background-size:70%;
  background-repeat:no-repeat;
  &:before {
    content:'';
    background-image:url(/img/pkt-network-top-asset.webp);
    position:absolute;
    top:0;
    right:0;
    width:75%;
    height:75%;
    background-position:right -300px top -175px;
    background-size:contain;
    background-repeat:no-repeat;
    z-index:1;
    @include for-width(-desktop-medium) {
      width:70%;
      height:70%;
      background-position:right -200px top -125px;
    }
    @include for-width(-tablet) {
      width:90%;
    }
    @include for-width(-small-lg) {
      width:100%;
      height:30%;
      background-position:left bottom 300px;
      background-size:cover;
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
      background-size:contain;
    }
  }
  & > section {
    z-index:3;
    position:relative;
  }
  & .c-spot-a-internal {
    @include for-width(-small-lg) {
      padding:rem(100) 0 rem(50);
    }
    &__title {
      max-width:rem(475);
      @include for-width(-small-lg) {
        max-width:rem(250);
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
          padding: rem(35);
        }
      }
    }
  }
  .v-asymetrical-section {
    & .first {
		  padding-top:rem(95);
      @include for-width(-tablet) {
        padding-top:0;
      }
	  }
    & .second {
		  & .green_dot:before {
        background-color: #0D4AE7;
      }
      & .blue_dot:before {
        background-color: #00B127;
      }
	  }
    & .container {
      @extend %df;
      @extend %jcsb;
      @extend %ais;
      padding:rem(190) 0 0;
      @include for-width(-laptop) {
        padding:rem(75) 0 rem(35);
      }
      @include for-width(-tablet) {
        display:block;
      }
      @include for-width(-small-lg) {
        padding:rem(95) rem(20) 0;
      }
    }
    &__heading {
      & h2 {
        @extend %h2-common;
        padding-bottom:rem(35);
        @include for-width(-small-lg) {
          padding-bottom:0;
        }
      }
      width:35%;
      @include for-width(-tablet) {
        width:100%;
        padding-bottom:rem(35);
      }
      @include for-width(-small-lg) {
        padding-bottom:rem(15);
      }
    }
    &__inner {
      width:65%;
      @include for-width(-tablet) {
        width:100%;
      }
      @include for-width(-small-lg) {
        padding:0 rem(20);
      }
    }
  }
}
</style>