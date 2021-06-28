<template>
  <div class="footer">
    <div class="margins">
    <div class="footer-ribbon">

      <div class="footer-ribbon-section" id="footer-left">
        <div class="address">
          <p class="address-name">Brown University</p>
          <div class="address-items">
            <p id="first-address-item"><MarkerIcon class="footer-address-svg"/>
                Providence, RI 02912</p>
            <p><PhoneIcon class="footer-address-svg"/>
                401-863-1000</p>
          </div>
        </div>
        <ul class="footer-quick-nav">
          <li><FooterLink url="https://www.brown.edu/about/visit" label="Visit Brown"></FooterLink></li>
          <li><FooterLink url="https://www.brown.edu/Facilities/Facilities_Management/maps/#building/" label="Campus Map"></FooterLink></li>
          <li><FooterLink url="https://www.brown.edu/a-z" label="A To Z"></FooterLink></li>
          <li><FooterLink url="https://www.brown.edu/about/contact-us" label="Contact Us"></FooterLink></li>
        </ul>
        <ul class="footer-quick-nav" id="footer-lower-nav">
          <li><FooterLink url="https://www.brown.edu/news" label="News"></FooterLink></li>
          <li><FooterLink url="https://events.brown.edu/" label="Events"></FooterLink></li>
          <li><FooterLink url="https://www.brown.edu/about/administration/public-safety/" label="Campus Safety"></FooterLink></li>
          <li><FooterLink url="https://www.brown.edu/website-accessibility" label="Accessibility"></FooterLink></li>
          <li><FooterLink url="https://www.brown.edu/about/administration/human-resources/employment-performance-development/jobsbrown" label="Careers at Brown"></FooterLink></li>
        </ul>
      </div>

      <div class="footer-ribbon-section" id="footer-right">
        <img class="footer-give-logo"
             src="https://www.brown.edu/sites/g/files/dprerj316/files/2019-04/logo_together.png"
             alt="Brown Together">
        <p class="footer-give-caption">The campaign for building on distinction</p>
        <FooterLink class="footer-give-link" url="https://giving.brown.edu/" label="GIVE TO BROWN"></FooterLink>
      </div>

    </div>
    </div>
    <div class="footer-sole">
      <ul class="footer-social-media">
        <li><a href="https://www.facebook.com/BrownUniversity">
            <FacebookLogo class="footer-social-svg" /></a></li>
        <li><a href="https://instagram.com/brownu">
            <InstagramLogo class="footer-social-svg" /></a></li>
        <li><a href="https://www.linkedin.com/edu/school?id=19348">
            <LinkedinLogo class="footer-social-svg" /></a></li>
        <li><a href="https://www.snapchat.com/add/brown-u">
            <SnapchatLogo class="footer-social-svg" /></a></li>
        <li><a href="https://twitter.com/BrownUniversity">
            <TwitterLogo class="footer-social-svg" /></a></li>
        <li><a href="https://www.youtube.com/brownuniversity">
            <YoutubeLogo class="footer-social-svg" /></a></li>
      </ul>
      <p class="copyright">© Brown University</p>
    </div>
  </div>
</template>

<script>
import FooterLink from '../components/FooterLink.vue';

import MarkerIcon from "../assets/icons/marker.svg";
import PhoneIcon from "../assets/icons/phone.svg";

import FacebookLogo from '../assets/icons/facebook.svg';
import InstagramLogo from '../assets/icons/instagram.svg';
import LinkedinLogo from '../assets/icons/linkedin.svg';
import SnapchatLogo from '../assets/icons/snapchat.svg';
import TwitterLogo from '../assets/icons/twitter.svg';
import YoutubeLogo from '../assets/icons/youtube.svg';


export default {
  name: 'Footer',
  components: {
    MarkerIcon,
    PhoneIcon,
    FooterLink,
    FacebookLogo,
    InstagramLogo,
    LinkedinLogo,
    SnapchatLogo,
    TwitterLogo,
    YoutubeLogo
  },
  data() {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer {
  line-height: 1.15;
  background-color: #4E3629;
  text-align: left;

  /* ----- variables ----- */

  /* breakpoints: */
  --sm: 576;
  --md: 740;
  --lg: 992;
  --xl: 1200;
  --xxl: 1370;
}

.footer ul {
  padding: 0px;
  margin: 0px;
}

.margins {
  display: flex;
  flex-wrap: wrap;
  margin-left: auto;
  margin-right: auto;
  min-width: 320px;
  width: calc(100% - 20px);
}

.footer-ribbon {
  display: flex;
  flex-direction: column;
  width: 100%;
  padding: 40px 0 50px;
}

@media (min-width: 740px) {
  .footer-ribbon {
    padding: 60px 0 70px;
  }
}
@media (min-width: 992px) {
  .footer-ribbon {
    flex-direction: row;
    padding: 90px 0 45px;
  }
}

.footer-ribbon-section {
  vertical-align: middle;
}

#footer-left {
  padding: 15px 50px 0px 50px;
}
@media (min-width: 992px) {
  #footer-left {
    border-right: 1px solid rgba(183, 176, 156, 0.2);
    width: calc(100% - 325px);
  }
}

.address-name {
  font-size: 11px;
  font-weight: 400;
  margin-bottom: 26px;
  text-transform: uppercase;
}
@media (min-width: 992px) {
  .address-name {
    font-size: 13px;
    letter-spacing: 1.5;
  }
}
@media (min-width: 992px) {
  .address-name {
    margin-bottom: 28px;
  }
}

.address-items {
  font-family: "MinionPro", serif;
  margin-bottom: 14px;
}
@media (min-width: 992px) {
  .address-items {
    margin-bottom: 12px;
  }
}
@media (max-width: 992px) {
  #first-address-item {
    margin-bottom: 14px;
  }
}

.address-items p {
  margin-top: 0px;
  display: block;
  padding-left: 25px;
  position: relative;
  vertical-align: middle;
  font-weight: 400;
  line-height: 1.3125;
}
@media (min-width: 740px) {
  .address-items p {
    font-size: 20px;
    line-height: 1.25;
  }
}
@media (min-width: 992px) {
  .address-items p {
    display: inline-block;
    margin-bottom: 0px;
    margin-right: 40px;
    font-size: 20px;
  }
}
@media (min-width: 1200px) {
  .address-items p {
    display: inline-block;
    margin-bottom: 0px;
    margin-right: 40px;
    font-size: 24px;
    line-height: 1.33333;
  }
}
.footer-address-svg {
  position: absolute;
  left: 0;
  top: 0;
  transform-origin: left top;
  height: 24px;
  width: 17px;
  vertical-align: middle;
  transform: scale(0.85);
  fill: rgba(255, 255, 255, 0.2);
}
@media (min-width: 992px) {
  .footer-address-svg {
    top: 2px;
  }
}

.footer-quick-nav {
  list-style-type: none;
  margin-bottom: 30px !important;
}
.footer-quick-nav li {
  display: inline-block;
  color: #FFC72C;
  text-transform: uppercase;
}
@media (max-width: 740px) {
  .footer-quick-nav {
    display: flex;
    flex-wrap: wrap;
  }
  .footer-quick-nav li {
    padding-right: 20px;
    width: 50%;
  }
}
@media (min-width: 740px) {
  .footer-quick-nav li {
    padding-right: 20px;
    width: 45%;
  }
}
@media (min-width: 1370px) {
  .footer-quick-nav {
    padding: 30px 0 35px;
  }
  .footer-quick-nav li {
    padding-right: 32px;
    width: auto;
  }
}

#footer-lower-nav {
  margin-bottom: 40px;
  padding: 30px 0 0px;
  border-top: 2px solid rgba(183, 176, 156, 0.2);
}
@media (max-width: 992px) {
  #footer-lower-nav {
    padding: 28px 0px;
    border-bottom: 2px solid rgba(183, 176, 156, 0.2);
    margin-bottom: 0px;
  }
}
@media (min-width: 1370px) {
  #footer-lower-nav {
    display: inline-block;
    vertical-align: top;
  }
}

#footer-right {
  padding-left: 50px;
  padding-right: 50px;
  align-items: center;
}
@media (min-width: 992px) {
  #footer-right {
    align-items: center;
    width: 325px;
    display: flex;
    flex-wrap: wrap;
    align-content: center;
  }
}

.footer-give-logo {
  max-width: 202px;
  width: 100%;
  margin-bottom: 18px;
}
.footer-give-caption {
  color: #B7B09C;
  font-family: "MinionPro", serif;
  font-size: 1.5rem;
  font-style: italic;
  font-weight: 400;
  line-height: 1.5;
  margin: 0 0 16px;
}
.footer-give-link {
  padding: 10px 0;
}

.address-name {
  font-family: "CircularStd", sans-serif;
  font-weight: 400;
  display: block;
  color: #B7B09C;
}

.address-items {
  display: inline-block;
  color: white;
}

.link-row {
  display: inline-block;
}

.footer-sole {
  padding: 2px 50px 0px 50px;
  background-color: rgba(0, 0, 0, 0.16);
  color: #B7B09C;
  font-family: "MinionPro", serif;
  font-size: 1.25rem;
  font-weight: 400;
}
@media (min-width: 740px) {
  .footer-sole {
    padding: 2px 50px 0px 50px;
    align-items: center;
    display: flex;
    flex-wrap: none;
    justify-content: space-between;
  }
}
.footer-social-media {
  list-style-type: none;
  align-items: center;
  display: flex;
  flex-wrap: wrap;
  margin: 0 -8px;
  padding: 0;
}
@media (min-width: 740px) {
  .footer-social-media {
    order: 2;
  }
}
.footer-social-media li {
  display: inline-block;
  vertical-align: middle;
  width: auto;
}
.footer-social-media a {
  padding: 19px 15px;
  box-shadow: inset 0 0 0 1px transparent;
  display: flex;
  justify-content: center;
  position: relative;
  text-align: center;
  transition: color 0.25s;
}
.footer-social-svg {
  height: 22px;
  width: 22px;
  fill: white;
}
.footer-social-svg:hover {
  fill: #FFC72C;
}

.copyright {
  border-top: 1px solid rgba(183, 176, 156, 0.2);
  font-size: 14px;
  font-weight: 400;
  margin: 0 -10px;
  padding-top: 20px;
  padding-bottom: 20px;
}
@media (min-width: 740px) {
  .copyright {
    border-top: 0;
    font-size: 20px;
    order: 1;
    padding-top: 0;
    padding-bottom: 0;
    position: relative;
    top: 2px;
  }
}
</style>
