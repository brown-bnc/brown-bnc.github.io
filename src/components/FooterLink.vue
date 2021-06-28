<template>
  <a :href="url" @mouseover="hover=true" @mouseleave="hover=false">
    {{ label }}
    <LinkIcon v-if="hover" class="footer-link-svg" />
    <ArrowRightIcon v-else class="footer-arrow-svg"/>
  </a>
</template>

<script>
import LinkIcon from '../assets/icons/link.svg';
import ArrowRightIcon from "../assets/icons/arrow-right.svg";

export default {
  name: 'FooterLink',
  components: {
    LinkIcon,
    ArrowRightIcon,
  },
  data() {
    return {
      hover: false
    }
  },
  props: {
    url: String,
    label: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
a {
  display: block;
  padding: 10px 0px;
  text-decoration: none;
  color: #FFC72C;
  font-family: "CircularStd", sans-serif;
  font-size: 0.8125rem;
  transition: background .25s, color .25s;
}

a:hover {
  color: white;
}

.footer-link-svg {
  display: inline;
  height: 14px;
  width: 14px;
  fill: white;
  vertical-align: middle;
}
.footer-arrow-svg {
  display: inline;
  height: 9px;
  width: 14px;
  vertical-align: middle;
  fill: #FFC72C;
}
</style>
