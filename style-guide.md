Skip to content
Product
Solutions
Open Source
Pricing


/*-----------------------------------*\
  #style.css
\*-----------------------------------*/

/**
 * copyright 2022 codewithsadee
 */





/*-----------------------------------*\
  #CUSTOM PROPERTY
\*-----------------------------------*/

:root {

  /**
   * colors
   */

  --rich-black-fogra-29_95: hsla(222, 18%, 11%, 0.95);
  --raisin-black-1: hsl(0, 0%, 16%);
  --raisin-black-2: hsl(236, 17%, 17%);
  --raisin-black-3: hsl(280, 11%, 11%);
  --raisin-black-4: hsl(280, 8%, 15%);
  --english-violet: hsl(274, 21%, 23%);
  --eerie-black-1: hsl(277, 25%, 10%);
  --eerie-black-2: hsl(280, 7%, 8%);
  --roman-silver: hsl(220, 6%, 59%);
  --quick-silver: hsl(0, 1%, 65%);
  --light-gray-1: hsl(0, 0%, 80%);
  --light-gray-2: hsl(0, 2%, 82%);
  --marigold_75: hsla(42, 99%, 46%, 0.75);
  --xiketic_90: hsla(280, 37%, 8%, 0.9);
  --cultured-2: hsl(0, 0%, 97%);
  --marigold: hsl(42, 99%, 46%);
  --platinum: hsl(0, 0%, 89%);
  --dim-gray: hsl(0, 0%, 42%);
  --white_15: hsla(0, 0%, 100%, 0.15);
  --white_10: hsla(0, 0%, 100%, 0.1);
  --xiketic: hsl(277, 25%, 10%);
  --silver: hsl(0, 0%, 78%);
  --white: hsl(0, 0%, 100%);
  --jet: hsl(236, 13%, 23%);

  /**
   * typography
   */

  --ff-oxanium: 'Oxanium', cursive;
  --ff-poppins: 'Poppins', sans-serif;

  --fs-1: 7rem;
  --fs-2: 4.5rem;
  --fs-3: 3.6rem;
  --fs-4: 2.4rem;
  --fs-5: 2.2rem;
  --fs-6: 2rem;
  --fs-7: 1.6rem;
  --fs-8: 1.5rem;
  --fs-9: 1.4rem;
  --fs-10: 1.3rem;
  --fs-11: 1.2rem;

  --fw-500: 500;
  --fw-600: 600;
  --fw-700: 700;
  --fw-800: 800;

  /**
   * spacing
   */

  --section-padding: 120px;

  /**
   * gradient
   */

  --gradient: radial-gradient(circle, hsl(250, 7%, 17%), hsl(250, 11%, 11%));

  /**
   * box shadow
   */

  --shadow-1: 0px 2px 8px 0px hsla(0, 0%, 0%, 0.2),
              inset 0px 2px 8px 0px hsla(0, 0%, 0%, 0.4);
  --shadow-2: 0px 5px 10px 1px hsla(0, 0%, 0%, 0.4);
  --shadow-3: 0px 5px 10px 1px hsla(219, 98%, 17%, 0.2);
  --shadow-4: 0px 5px 10px 1px hsla(0, 0%, 0%, 0.15);

  /**
   * transition
   */

  --transition: 0.25s ease;
  --cubic-out: cubic-bezier(0.33, 0.85, 0.4, 0.96);

}





/*-----------------------------------*\
  #RESET
\*-----------------------------------*/

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

li { list-style: none; }

a {
  text-decoration: none;
  color: inherit;
}

a,
img,
span,
time,
input,
button,
ion-icon { display: block; }

img { height: auto; }

input,
button {
  background: none;
  border: none;
  font: inherit;
}

input { width: 100%; }

button { cursor: pointer; }

ion-icon { pointer-events: none; }

address { font-style: normal; }

html {
  font-family: var(--ff-poppins);
  font-size: 10px;
  scroll-behavior: smooth;
}

body {
  background-color: var(--raisin-black-3);
  font-size: 1.6rem;
  line-height: 1.5;
}

:focus-visible { outline-offset: 4px; }





/*-----------------------------------*\
  #REUSED STYLE
\*-----------------------------------*/

.container { padding-inline: 15px; }

.section { padding-block: var(--section-padding); }

.h1,
.h2,
.h3 {
  color: var(--white);
  font-family: var(--ff-oxanium);
  font-weight: var(--fw-800);
  line-height: 1;
}

.h1 {
  font-size: var(--fs-2);
  letter-spacing: -3px;
}

.h2 { font-size: var(--fs-3); }

.h3 {
  font-size: var(--fs-6);
  text-transform: uppercase;
}

:is(.h1, .h2, .h3, .card-price) .span {
  display: inline-block;
  color: var(--marigold);
}

.btn {
  margin-inline: auto;
  color: var(--eerie-black-1);
  font-size: var(--fs-8);
  text-transform: uppercase;
  font-weight: var(--fw-700);
  min-height: 55px;
  padding-inline: 35px;
}

.skewBg {
  position: relative;
  z-index: 1;
}

.skewBg::before {
  content: "";
  position: absolute;
  inset: 0;
  transform: skewX(var(--skewX, -16deg));
  background-color: var(--bg, var(--marigold));
  z-index: -1;
}

.btn::after {
  content: "";
  position: absolute;
  top: 0;
  bottom: 0;
  left: calc(100% + 8px);
  width: 5px;
  transform: skewX(-16deg) translateX(var(--translateX, 0));
  background-color: var(--marigold);
  transition: var(--transition);
}

.btn:is(:hover, :focus)::after { --translateX: -13px; }

.has-scrollbar {
  display: flex;
  gap: 30px;
  overflow-x: auto;
  padding-block-end: 30px;
  scroll-snap-type: inline mandatory;
}

.has-scrollbar::-webkit-scrollbar { height: 10px; }

.has-scrollbar::-webkit-scrollbar-track { outline: 3px solid var(--marigold); }

.has-scrollbar::-webkit-scrollbar-thumb { background-color: var(--marigold); }

.has-scrollbar::-webkit-scrollbar-button { width: calc(25% - 40px); }

.section-subtitle,
.section-title {
  position: relative;
  text-align: center;
  text-transform: uppercase;
}

.section-subtitle {
  color: var(--silver);
  font-size: var(--fs-9);
  font-weight: var(--fw-700);
  margin-block-end: 10px;
}

.section-title::after {
  content: url("../images/title-underline.png");
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translateX(-50%);
}

.scrollbar-item {
  min-width: 100%;
  scroll-snap-align: start;
}

.card-banner { background-color: var(--light-gray-1); }

.img-holder { aspect-ratio: var(--width) / var(--height); }

.img-cover {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-badge {
  min-height: 30px;
  color: var(--eerie-black-1);
  font-size: var(--fs-11);
  font-weight: var(--fw-700);
  text-transform: uppercase;
  max-width: max-content;
  display: grid;
  align-items: center;
  padding-inline: 20px;
}

.card-badge::before { --skewX: -10deg; }

.w-100 { width: 100%; }

.section-text {
  color: var(--color, var(--light-gray-1));
  font-size: var(--fs-8);
  font-weight: var(--fw-500);
  max-width: 65ch;
  margin-inline: auto;
  text-align: center;
  line-height: 1.8;
}





/*-----------------------------------*\
  #HEADER
\*-----------------------------------*/

.header-top,
.cart-btn,
.header-bottom::before,
.navbar-link::before { display: none; }

.header {
  position: relative;
  min-height: 1px;
}

.header-bottom {
  position: absolute;
  top: calc(100% - 1px);
  left: 0;
  width: 100%;
  background-color: var(--raisin-black-2);
  padding-block: 20px;
  z-index: 4;
}

.header-bottom.active {
  position: fixed;
  top: -85px;
  animation: slideIn 0.5s var(--cubic-out) forwards;
}

@keyframes slideIn {
  0% { transform: translateY(0); }
  100% { transform: translateY(100%); }
}

.header-bottom .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  color: var(--white);
  font-family: var(--ff-oxanium);
  font-size: 3rem;
  font-weight: var(--fw-800);
}

.header-actions {
  display: flex;
  align-items: center;
  gap: 20px;
}

.search-btn {
  color: var(--marigold);
  padding: 13px;
  box-shadow: var(--shadow-1);
  border-radius: 4px;
}

.search-btn ion-icon { --ionicon-stroke-width: 80px; }

.nav-toggle-btn {
  color: var(--white);
  font-size: 30px;
  border: 1px solid var(--white);
  padding: 4px;
}

.nav-toggle-btn.active .menu,
.nav-toggle-btn .close { display: none; }

.nav-toggle-btn .menu,
.nav-toggle-btn.active .close { display: block; }

.navbar {
  background-color: var(--eerie-black-1);
  color: var(--white);
  position: absolute;
  top: 100%;
  right: 0;
  width: 100%;
  max-width: 350px;
  visibility: hidden;
  max-height: 0;
  transition: 0.25s var(--cubic-out);
  overflow: hidden;
}

.navbar.active {
  visibility: visible;
  max-height: 275px;
  transition-duration: 0.5s;
}

.navbar-item:not(:last-child) { border-block-end: 1px solid var(--white_15); }

.navbar-link {
  padding: 10px 25px;
  transition: var(--transition);
}

.navbar-link:is(:hover, :focus) { background-color: var(--white_10); }





/*-----------------------------------*\
  #SEARCH BOX
\*-----------------------------------*/

.search-container {
  background-color: var(--rich-black-fogra-29_95);
  position: fixed;
  inset: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-inline: 40px;
  z-index: 6;
  visibility: hidden;
  opacity: 0;
  transition: var(--transition);
}

.search-container.active {
  visibility: visible;
  opacity: 1;
}

.search-container .input-wrapper {
  position: relative;
  max-width: 560px;
  width: 100%;
}

.search-container .search-field {
  color: var(--white);
  font-size: 2rem;
  padding: 20px;
  padding-inline-end: 60px;
  border-block-end: 3px solid var(--white_10);
  outline: none;
  transition: var(--transition);
}

.search-container .search-field:focus { border-color: var(--light-gray-2); }

.search-container .search-field::-webkit-search-cancel-button { display: none; }

.search-container .search-submit {
  position: absolute;
  top: 50%;
  right: 20px;
  transform: translateY(-50%);
  font-size: 25px;
  color: var(--marigold);
}

.search-container .search-submit ion-icon { --ionicon-stroke-width: 70px; }

.search-container .search-close {
  position: fixed;
  inset: 0;
  cursor: default;
  z-index: -1;
}





/*-----------------------------------*\
  #HERO
\*-----------------------------------*/

.hero-banner { display: none; }

.hero {
  --section-padding: 60px;
  margin-block-start: 84px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  text-align: center;
  min-height: 100vh;
  display: grid;
  align-items: center;
}

.hero-subtitle {
  color: var(--marigold);
  font-size: var(--fs-6);
  font-weight: var(--fw-700);
  text-transform: uppercase;
}

.hero-title { margin-block: 15px 12px; }

.hero-text {
  color: var(--light-gray-2);
  margin-block-end: 45px;
}





/*-----------------------------------*\
  #BRAND
\*-----------------------------------*/

.brand {
  --section-padding: 60px;
  background-image: var(--gradient);
}

.brand .has-scrollbar { padding-block-end: 0; }

.brand .has-scrollbar::-webkit-scrollbar { display: none; }

.brand-item {
  min-width: calc(50% - 10px);
  scroll-snap-align: start;
}

.brand-item > img { margin-inline: auto; }





/*-----------------------------------*\
  #LATEST GAME
\*-----------------------------------*/

.section-wrapper {
  position: relative;
  background-color: var(--white);
  z-index: 1;
}

.section-wrapper::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 57%;
  background-image: url("../images/section-wrapper-bg.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  z-index: -1;
}

.latest-game .section-title { margin-block-end: 80px; }

.latest-game .has-scrollbar {
  margin-inline: -15px;
  padding-inline: 15px;
  scroll-padding-inline-start: 15px;
}

.latest-game-card {
  position: relative;
  box-shadow: var(--shadow-2);
}

.latest-game-card .card-content {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: var(--xiketic_90);
  padding: 35px 25px;
}

.latest-game-card .card-badge {
  position: absolute;
  bottom: 100%;
  left: 25px;
}

.latest-game-card .card-title {
  margin-block-end: 12px;
  transition: var(--transition);
}

.latest-game-card .card-title:is(:hover, :focus) { color: var(--marigold); }

.latest-game-card .card-price {
  color: var(--silver);
  font-size: var(--fs-10);
  font-weight: var(--fw-600);
}

.latest-game-card .card-price .span { margin-inline-start: 5px; }





/*-----------------------------------*\
  #LIVE MATCH
\*-----------------------------------*/

.live-match {
  padding-block-start: 0;
  overflow-x: hidden;
}

.live-match .section-title { margin-block-end: 90px; }

.live-match-banner {
  position: relative;
  background-color: var(--light-gray-1);
  border-radius: 6px;
  overflow: hidden;
  box-shadow: var(--shadow-3);
}

.live-match-banner .play-btn {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: var(--marigold);
  font-size: 60px;
}

.live-match-player {
  position: relative;
  padding-block-start: var(--section-padding);
}

.live-match-player::after {
  content: "LIVE";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -40%);
  font-size: 15rem;
  font-weight: var(--fw-600);
  color: var(--cultured-2);
  z-index: -1;
}

.live-match-player .player { max-width: max-content; }

.live-match-player .player-2 { margin-inline-start: auto; }

.live-match-detail { margin-block: 50px; }

.live-match-subtitle {
  background-color: var(--marigold);
  color: var(--white);
  font-size: var(--fs-9);
  text-transform: uppercase;
  font-weight: var(--fw-700);
  letter-spacing: 2px;
  padding: 4px 20px;
  max-width: max-content;
  margin-inline: auto;
  margin-block-end: 30px;
}

.live-match-time {
  color: var(--xiketic);
  font-size: var(--fs-1);
  font-weight: var(--fw-700);
  max-width: max-content;
  margin-inline: auto;
  line-height: 1;
}





/*-----------------------------------*\
  #FEATURED GAME
\*-----------------------------------*/

.featured-game { background-color: var(--cultured-2); }

.featured-game .section-title {
  color: var(--xiketic);
  margin-block-end: 90px;
}

.featured-game .has-scrollbar { gap: 0; }

.featured-game-card { position: relative; }

.featured-game-card :is(.card-content, .card-content-overlay) { position: absolute; }

.featured-game-card .card-content {
  bottom: 0;
  left: 0;
  right: 0;
  padding: 30px 35px;
  transition: var(--transition);
}

.featured-game-card .card-content-overlay {
  inset: 0;
  background-color: var(--marigold_75);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  opacity: 0;
  transition: var(--transition);
}

.featured-game-card .card-title { margin-block-end: 5px; }

.featured-game-card .card-meta {
  color: var(--white);
  font-size: var(--fs-11);
  font-weight: var(--fw-500);
  text-transform: uppercase;
  display: flex;
  align-items: center;
  gap: 4px;
}

.featured-game-card .card-content .card-meta { color: var(--platinum); }

.featured-game-card .card-content ion-icon {
  color: var(--marigold);
  font-size: 14px;
}

.featured-game-card .card-icon { margin-block-end: 20px; }

.featured-game-card .card-content-overlay .card-title { color: var(--xiketic); }

.featured-game-card .card-content-overlay .span { color: var(--white); }

.featured-game-card:is(:hover, :focus-within) .card-content { opacity: 0; }

.featured-game-card:is(:hover, :focus-within) .card-content-overlay { opacity: 1; }





/*-----------------------------------*\
  #SHOP
\*-----------------------------------*/

.shop {
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.shop .section-text { margin-block: 50px 60px; }

.shop .has-scrollbar {
  margin-inline: -15px;
  padding-inline: 15px;
  scroll-padding-inline-start: 15px;
}

.shop-card {
  box-shadow: var(--shadow-4);
  height: 100%;
}

.shop-card .card-content {
  position: relative;
  padding: 25px;
  padding-block-start: 40px;
}

.shop-card .card-badge {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%);
}

.shop-card .h3 { font-size: var(--fs-7); }

.shop-card .card-title {
  transition: var(--transition);
  margin-block-end: 10px;
}

.shop-card .card-title:is(:hover, :focus) { color: var(--marigold); }

.shop-card .card-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: var(--marigold);
}

.shop-card .card-price {
  font-family: var(--ff-oxanium);
  font-weight: var(--fw-800);
}

.shop-card .card-btn {
  color: inherit;
  font-size: 18px;
  padding: 7px;
  border: 1px solid var(--english-violet);
  border-radius: 4px;
  transition: var(--transition);
}

.shop-card .card-btn:is(:hover, :focus) {
  background-color: var(--marigold);
  color: var(--xiketic);
  border-color: var(--marigold);
}




/*-----------------------------------*\
  #BLOG
\*-----------------------------------*/

.blog { background-color: var(--white); }

.blog .section-title { color: var(--xiketic); }

.blog .section-text {
  color: var(--dim-gray);
  margin-block: 50px 60px;
}

.blog-list {
  display: grid;
  gap: 50px;
}

.blog-card .card-banner { margin-block-end: 30px; }

.blog-card .card-meta-list {
  display: flex;
  align-items: center;
  gap: 20px;
}

.blog-card .card-meta-item {
  display: flex;
  align-items: center;
  gap: 5px;
  color: var(--quick-silver);
  font-size: var(--fs-11);
  font-weight: var(--fw-600);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.blog-card .card-meta-item ion-icon {
  --ionicon-stroke-width: 50px;
  color: var(--marigold);
}

.blog-card .card-meta-item a.item-text { transition: var(--transition); }

.blog-card .card-meta-item a.item-text:is(:hover, :focus) { color: var(--marigold); }

.blog-card .card-title {
  color: var(--raisin-black-1);
  font-size: var(--fs-5);
  font-family: var(--ff-oxanium);
  font-weight: var(--fw-800);
  text-transform: uppercase;
  line-height: 1.2;
  margin-block: 10px 15px;
  transition: var(--transition);
}

.blog-card .card-title:is(:hover, :focus) { color: var(--marigold); }

.blog-card .card-text {
  color: var(--dim-gray);
  font-size: var(--fs-8);
  font-weight: var(--fw-500);
  line-height: 1.8;
  margin-block-end: 25px;
}

.blog-card .card-link {
  color: var(--raisin-black-1);
  font-size: var(--fs-9);
  font-weight: var(--fw-700);
  text-transform: uppercase;
  display: flex;
  align-items: center;
  gap: 4px;
  transition: var(--transition);
}

.blog-card .card-link ion-icon,
.blog-card .card-link:is(:hover, :focus) { color: var(--marigold); }





/*-----------------------------------*\
  #NEWSLETTER
\*-----------------------------------*/

.newsletter { margin-block-end: 80px; }

.newsletter-card {
  background-color: var(--raisin-black-3);
  padding: 40px 15px;
  margin-block-start: -55px;
  border-radius: 80px;
}

.newsletter .h2 {
  font-size: var(--fs-4);
  text-transform: uppercase;
  text-align: center;
  margin-block-end: 30px;
}

.newsletter .input-wrapper {
  max-width: 300px;
  margin-inline: auto;
  margin-block-end: 10px;
}

.newsletter .email-field {
  font-size: var(--fs-9);
  color: var(--white);
  font-weight: var(--fw-500);
  padding: 17px 45px;
  padding-inline-end: 20px;
  outline: none;
}

.newsletter .input-wrapper ion-icon {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  left: 20px;
  color: var(--marigold);
  --ionicon-stroke-width: 50px;
}

.newsletter .input-wrapper::before {
  --bg: var(--raisin-black-4);
  --skewX: -20deg;
}

.newsletter-btn {
  font-size: var(--fs-9);
  display: flex;
  align-items: center;
  gap: 5px;
  padding-inline: 20px;
  transition: var(--transition);
}

.newsletter-btn::after { display: none; }

.newsletter-btn::before {
  --skewX: -20deg;
  transition: var(--transition);
}

.newsletter-btn:is(:hover, :focus) { color: var(--marigold); }

.newsletter-btn:is(:hover, :focus)::before { background-color: var(--white); }





/*-----------------------------------*\
  #FOOTER
\*-----------------------------------*/

.footer { color: var(--roman-silver); }

.footer-top { padding-block-end: var(--section-padding); }

.footer-top .container {
  display: grid;
  gap: 50px;
}

.footer .logo { margin-block-end: 35px; }

.footer-text,
.footer .contact-item {
  font-size: var(--fs-8);
  font-weight: var(--fw-500);
  line-height: 1.8;
}

.footer-text { margin-block-end: 15px; }

.contact-item:not(:last-child) { margin-block-end: 10px; }

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 10px;
}

.contact-icon {
  margin-block-start: 3px;
  font-size: 17px;
}

.footer-list-title {
  position: relative;
  color: var(--silver);
  font-family: var(--ff-oxanium);
  text-transform: uppercase;
  font-weight: var(--fw-800);
  padding-block-end: 20px;
  margin-block-end: 35px;
}

.footer-list-title::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 30px;
  height: 3px;
  background-color: var(--marigold);
}

.footer-link {
  font-size: var(--fs-9);
  max-width: max-content;
  transition: var(--transition);
  padding-block: 8px;
  font-weight: var(--fw-500);
}

.footer-link:is(:hover, :focus) {
  color: var(--marigold);
  transform: translateX(5px);
}

.footer .social-wrapper { margin-block-end: 50px; }

.footer .social-list {
  display: flex;
  gap: 10px;
}

.footer .social-link {
  color: var(--white);
  padding: 10px;
  border-radius: 2px;
}

.footer-newsletter { position: relative; }

.footer-newsletter .email-field {
  background-color: var(--raisin-black-4);
  padding: 12px 20px;
  padding-inline-end: 60px;
  font-size: var(--fs-9);
  color: var(--white);
}

.footer-btn {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 53px;
  background-color: var(--marigold);
  color: var(--xiketic);
  display: grid;
  place-content: center;
}

.footer-bottom-img { display: none; }

.footer-bottom {
  background-color: var(--eerie-black-2);
  padding-block: 20px;
  text-align: center;
}

.copyright {
  font-size: var(--fs-9);
  font-weight: var(--fw-500);
  line-height: 1.8;
}

.copyright-link {
  display: inline-block;
  color: var(--marigold);
}





/*-----------------------------------*\
  #BACK TO TOP
\*-----------------------------------*/

.back-top-btn {
  position: fixed;
  bottom: 10px;
  right: 15px;
  background-color: var(--marigold);
  padding: 12px;
  z-index: 4;
  transition: var(--transition);
  opacity: 0;
  visibility: hidden;
}

.back-top-btn.active {
  opacity: 1;
  visibility: visible;
  transform: translateY(-10px);
}




/*-----------------------------------*\
  #MEDIA QUERIES
\*-----------------------------------*/

/**
 * responsive for larger than 576px screen
 */

@media (min-width: 576px) {

  /**
   * REUSED STYLE
   */

  .container {
    max-width: 540px;
    width: 100%;
    margin-inline: auto;
  }

  .h1 { --fs-2: 7rem; }



  /**
   * HEADER
   */

  .header-actions { gap: 40px; }

  .cart-btn {
    display: block;
    position: relative;
    color: var(--white);
    font-size: 20px;
  }

  .cart-badge {
    position: absolute;
    top: -6px;
    right: -10px;
    background-color: var(--marigold);
    color: var(--eerie-black-1);
    font-size: var(--fs-11);
    border-radius: 20px;
    padding: 3px 5px;
    line-height: 1;
    font-weight: var(--fw-800);
  }



  /**
   * SEARCH BOX
   */

  .search-container :is(.search-field, .search-submit) { font-size: var(--fs-3); }



  /**
   * BRAND
   */

  .brand-item { min-width: calc(33.33% - 13.33px); }



  /**
   * FEATURED GAME 
   */

  .featured-game .scrollbar-item { min-width: 50%; }



  /**
   * BLOG
   */

  .blog-list {
    grid-template-columns: 75%;
    justify-content: center;
  }



  /**
   * FOOTER
   */

  .footer-top .container { grid-template-columns: 1fr 1fr; }

  .footer-brand,
  .footer-wrapper { grid-column: 1 / 3; }

}





/**
 * responsive for larger than 768px screen
 */

@media (min-width: 768px) {

  /**
   * REUSED STYLE
   */

  .container { max-width: 720px; }

  .scrollbar-item { min-width: calc(50% - 15px); }



  /**
   * HERO
   */

  .hero-text {
    max-width: 60ch;
    margin-inline: auto;
  }



  /**
   * BRAND
   */

  .brand-item { min-width: calc(25% - 15px); }



  /**
   * LIVE MATCH
   */

  .live-match-banner .play-btn { font-size: 120px; }

  .live-match-player::after { font-size: 30rem; }



  /**
   * BLOG
   */

  .blog-list { grid-template-columns: 1fr 1fr; }



  /**
   * NEWSLETTER
   */

  .newsletter :is(.input-wrapper, .newsletter-btn) { margin: 0; }

  .newsletter .input-wrapper {
    max-width: unset;
    width: 100%;
  }

  .newsletter .h2 { --fs-4: 2.6rem; }

  .newsletter-form {
    display: flex;
    gap: 10px;
    max-width: 500px;
    width: 100%;
    margin-inline: auto;
  }



  /**
   * FOOTER
   */

  .footer-brand,
  .footer-wrapper { grid-column: auto; }

  .footer-bottom-img { display: block; }

  .footer-bottom { text-align: left; }

  .footer-bottom .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
  }



  /**
   * BACK TO TOP
   */

  .back-top-btn {
    bottom: 50px;
    right: 45px;
  }

}





/**
 * responsive for larger than 992px screen
 */

@media (min-width: 992px) {

  /**
   * REUSED STYLE
   */

  .container { max-width: 960px; }

  :is(.header, .hero, .live-match) .container { max-width: unset; }

  .scrollbar-item { min-width: calc(33.33% - 20px); }



  /**
   * HEADER
   */

  .header-top {
    display: block;
    background-image: url("../images/header-top-bg.jpg");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    width: 100%;
    padding-block: 20px;
  }

  .header-top .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .countdown-text {
    color: var(--quick-silver);
    font-size: var(--fs-10);
    font-weight: var(--fw-600);
  }

  .countdown-text .span {
    display: inline-block;
    color: var(--xiketic);
    font-size: 1.8rem;
    font-weight: var(--fw-700);
    padding: 10px 20px;
    margin-inline: 5px;
  }

  .header :is(.social-wrapper, .social-list) {
    display: flex;
    align-items: center;
  }

  .header .social-wrapper { gap: 15px; }

  .header .social-list { gap: 10px; }

  .social-title {
    color: var(--white);
    font-family: var(--ff-oxanium);
    font-size: var(--fs-8);
    font-weight: var(--fw-700);
  }

  .header .social-link {
    background-color: var(--jet);
    color: var(--marigold);
    font-size: var(--fs-9);
    padding: 8px 10px;
  }

  .header-bottom { outline: 1px solid hsla(0, 0%, 0%, 0.2); }

  .header-bottom::before {
    display: block;
    top: 0;
    left: -15px;
    right: auto;
    width: 170px;
    --skewX: 16deg;
  }

  .nav-toggle-btn { display: none; }

  .navbar,
  .navbar.active {
    all: unset;
    margin-inline: auto 15px;
  }

  .navbar-list { display: flex; }

  .navbar-item:not(:last-child) { border-block-end: none; }

  .navbar-link {
    color: var(--white);
    font-family: var(--ff-oxanium);
    font-size: var(--fs-11);
    text-transform: uppercase;
    font-weight: var(--fw-700);
    padding: 10px 20px;
  }

  .navbar-link::before {
    display: block;
    opacity: 0;
    transition: var(--transition);
  }

  .navbar-link:is(:hover, :focus) {
    background-color: transparent;
    color: var(--xiketic);
  }

  .navbar-link:is(:hover, :focus)::before { opacity: 1; }



  /**
   * HERO
   */

  .hero { text-align: left; }

  .hero-banner { display: block; }

  .hero .container {
    display: grid;
    grid-template-columns: 1fr 0.9fr;
    align-items: center;
    gap: 50px;
  }

  .btn { margin-inline: 0; }



  /**
   * BRAND
   */

  .brand-item { min-width: calc(20% - 16px); }



  /**
   * LATEST GAME
   */

  .latest-game .has-scrollbar { padding-block-end: 0; }



  /**
   * LIVE MATCH
   */

  .live-match-banner {
    max-width: 700px;
    margin-inline: auto;
  }

  .live-match-player {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    align-items: center;
  }

  .live-match-detail { margin-block: 0; }



  /**
   * FEATURED GAME
   */

  .featured-game .scrollbar-item { min-width: 33.33%; }



  /**
   * BLOG
   */

  .blog-list {
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
  }



  /**
   * NEWSLETTER
   */

  .newsletter-form { max-width: 650px; }



  /**
   * FOOTER
   */

  .footer .container {
    grid-template-columns: 1fr 0.7fr 0.7fr;
    column-gap: 80px;
  }

}





/**
 * responsive for larger than 1200px screen
 */

@media (min-width: 1200px) {

  /**
   * REUSED STYLE
   */

  .container,
  :is(.header, .hero, .live-match) .container { max-width: 1230px; }

  .h1 { --fs-2: 7.5rem; }

  .scrollbar-item { min-width: calc(25% - 22.5px); }



  /**
   * HEADER
   */

  .header-bottom::before { width: 270px; }

  .navbar-link {
    font-size: var(--fs-9);
    padding-inline: 25px;
  }



  /**
   * HERO
   */

  .hero .container { grid-template-columns: 1fr 1fr; }



  /**
   * BRAND
   */

  .brand-item { min-width: calc(16.66% - 16.66px); }



  /**
   * LIVE MATCH
   */

  .section-wrapper::before { height: 72%; }

  .live-match-banner { max-width: max-content; }

  .live-match-player::after { font-size: 35rem; }



  /**
   * FEATURED GAME
   */

  .featured-game .has-scrollbar { padding-block-end: 0; }

  .featured-game .scrollbar-item { min-width: 25%; }



  /**
   * SHOP
   */

  .shop .has-scrollbar { padding-block-end: 15px; }



  /**
   * NEWSLETTER
   */

  .newsletter-card {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-inline: 70px;
  }

  .newsletter .h2 { margin-block-end: 0; }

  .newsletter-form { margin-inline: 0; }



  /**
   * FOOTER
   */

  .footer .container { grid-template-columns: 1fr 0.7fr 0.7fr 1fr; }

}
 Binary file addedBIN +59.2 KB 
Gamics/assets/images/blog-1.jpg

 Binary file addedBIN +64.2 KB 
Gamics/assets/images/blog-2.jpg

 Binary file addedBIN +51.7 KB 
Gamics/assets/images/blog-3.jpg

 Binary file addedBIN +1.27 KB 
Gamics/assets/images/brand-1.png

 Binary file addedBIN +1.5 KB 
Gamics/assets/images/brand-2.png

 Binary file addedBIN +1.42 KB 
Gamics/assets/images/brand-3.png

 Binary file addedBIN +1.36 KB 
Gamics/assets/images/brand-4.png

 Binary file addedBIN +1.63 KB 
Gamics/assets/images/brand-5.png

 Binary file addedBIN +1.21 KB 
Gamics/assets/images/brand-6.png

 Binary file addedBIN +27.6 KB 
Gamics/assets/images/featured-game-1.jpg

 Binary file addedBIN +57.4 KB 
Gamics/assets/images/featured-game-2.jpg

 Binary file addedBIN +47.1 KB 
Gamics/assets/images/featured-game-3.jpg

 Binary file addedBIN +42.1 KB 
Gamics/assets/images/featured-game-4.jpg

 Binary file addedBIN +743 Bytes 
Gamics/assets/images/featured-game-icon.png

 Binary file addedBIN +1.62 KB 
Gamics/assets/images/footer-bottom-img.png

 Binary file addedBIN +1.52 KB 
Gamics/assets/images/header-top-bg.jpg

 Binary file addedBIN +121 KB 
Gamics/assets/images/hero-banner.png

 Binary file addedBIN +276 KB 
Gamics/assets/images/hero-bg.jpg

 Binary file addedBIN +38.5 KB 
Gamics/assets/images/latest-game-1.jpg

 Binary file addedBIN +43.8 KB 
Gamics/assets/images/latest-game-2.jpg

 Binary file addedBIN +102 KB 
Gamics/assets/images/latest-game-3.jpg

 Binary file addedBIN +132 KB 
Gamics/assets/images/live-match-banner.jpg

 Binary file addedBIN +16.8 KB 
Gamics/assets/images/live-match-player-1.png

 Binary file addedBIN +17.7 KB 
Gamics/assets/images/live-match-player-2.png

 Binary file addedBIN +113 KB 
Gamics/assets/images/section-wrapper-bg.png

 Binary file addedBIN +11.8 KB 
Gamics/assets/images/shop-bg.jpg

 Binary file addedBIN +6.92 KB 
Gamics/assets/images/shop-img-1.jpg

 Binary file addedBIN +8.05 KB 
Gamics/assets/images/shop-img-2.jpg

 Binary file addedBIN +4.59 KB 
Gamics/assets/images/shop-img-3.jpg

 Binary file addedBIN +4.2 KB 
Gamics/assets/images/shop-img-4.jpg

 Binary file addedBIN +636 Bytes 
Gamics/assets/images/title-underline.png

 53 changes: 53 additions & 0 deletions53  
Gamics/assets/js/script.js
@@ -0,0 +1,53 @@
'use strict';



const navbar = document.querySelector("[data-navbar]");
const navbarLinks = document.querySelectorAll("[data-nav-link]");
const navbarToggler = document.querySelector("[data-nav-toggler]");

navbarToggler.addEventListener("click", function () {
  navbar.classList.toggle("active");
  this.classList.toggle("active");
});

for (let i = 0; i < navbarLinks.length; i++) {
  navbarLinks[i].addEventListener("click", function () {
    navbar.classList.remove("active");
    navbarToggler.classList.remove("active");
  });
}



/**
 * search toggle
 */

const searchTogglers = document.querySelectorAll("[data-search-toggler]");
const searchBox = document.querySelector("[data-search-box]");

for (let i = 0; i < searchTogglers.length; i++) {
  searchTogglers[i].addEventListener("click", function () {
    searchBox.classList.toggle("active");
  });
}



/**
 * header
 */

const header = document.querySelector("[data-header]");
const backTopBtn = document.querySelector("[data-back-top-btn]");

window.addEventListener("scroll", function () {
  if (window.scrollY >= 200) {
    header.classList.add("active");
    backTopBtn.classList.add("active");
  } else {
    header.classList.remove("active");
    backTopBtn.classList.remove("active");
  }
});
 4 changes: 4 additions & 0 deletions4  
Gamics/favicon.svg

 1,165 changes: 1,165 additions & 0 deletions1,165  
Gamics/index.html
@@ -0,0 +1,1165 @@
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gamics - Create Manage Matches</title>

  <!-- 
    - favicon
  -->
  <link rel="shortcut icon" href="./favicon.svg" type="image/svg+xml">

  <!-- 
    - custom css link
  -->
  <link rel="stylesheet" href="./assets/css/style.css">

  <!-- 
    - google font link
  -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link
    href="https://fonts.googleapis.com/css2?family=Oxanium:wght@600;700;800&family=Poppins:wght@400;500;600;700;800;900&display=swap"
    rel="stylesheet">

  <!-- 
    - preload images
  -->
</head>

<body id="top">

  <!-- 
    - #HEADER
  -->

  <header class="header">

    <div class="header-top">
      <div class="container">

        <div class="countdown-text">
          Exclusive Black Friday ! Offer <span class="span skewBg">10</span> Days
        </div>

        <div class="social-wrapper">

          <p class="social-title">Follow us on :</p>

          <ul class="social-list">

            <li>
              <a href="#" class="social-link">
                <ion-icon name="logo-facebook"></ion-icon>
              </a>
            </li>

            <li>
              <a href="#" class="social-link">
                <ion-icon name="logo-twitter"></ion-icon>
              </a>
            </li>

            <li>
              <a href="#" class="social-link">
                <ion-icon name="logo-pinterest"></ion-icon>
              </a>
            </li>

            <li>
              <a href="#" class="social-link">
                <ion-icon name="logo-linkedin"></ion-icon>
              </a>
            </li>

          </ul>

        </div>

      </div>
    </div>

    <div class="header-bottom skewBg" data-header>
      <div class="container">

        <a href="#" class="logo">Gamics</a>

        <nav class="navbar" data-navbar>
          <ul class="navbar-list">

            <li class="navbar-item">
              <a href="#home" class="navbar-link skewBg" data-nav-link>Home</a>
            </li>

            <li class="navbar-item">
              <a href="#live" class="navbar-link skewBg" data-nav-link>Live</a>
            </li>

            <li class="navbar-item">
              <a href="#features" class="navbar-link skewBg" data-nav-link>Features</a>
            </li>

            <li class="navbar-item">
              <a href="#shop" class="navbar-link skewBg" data-nav-link>Shop</a>
            </li>

            <li class="navbar-item">
              <a href="#blog" class="navbar-link skewBg" data-nav-link>Blog</a>
            </li>

            <li class="navbar-item">
              <a href="#" class="navbar-link skewBg" data-nav-link>Contact</a>
            </li>

          </ul>
        </nav>

        <div class="header-actions">

          <button class="cart-btn" aria-label="cart">
            <ion-icon name="cart"></ion-icon>

            <span class="cart-badge">0</span>
          </button>

          <button class="search-btn" aria-label="open search" data-search-toggler>
            <ion-icon name="search-outline"></ion-icon>
          </button>

          <button class="nav-toggle-btn" aria-label="toggle menu" data-nav-toggler>
            <ion-icon name="menu-outline" class="menu"></ion-icon>
            <ion-icon name="close-outline" class="close"></ion-icon>
          </button>

        </div>

      </div>
    </div>

  </header>





  <!-- 
    - #SEARCH BOX
  -->

  <div class="search-container" data-search-box>

    <div class="input-wrapper">
      <input type="search" name="search" aria-label="search" placeholder="Search here..." class="search-field">

      <button class="search-submit" aria-label="submit search" data-search-toggler>
        <ion-icon name="search-outline"></ion-icon>
      </button>

      <button class="search-close" aria-label="close search" data-search-toggler></button>
    </div>

  </div>





  <main>
    <article>

      <!-- 
        - #HERO
      -->

      <section class="section hero" id="home" aria-label="home"
        style="background-image: url('./assets/images/hero-bg.jpg')">
        <div class="container">

          <div class="hero-content">

            <p class="hero-subtitle">World Gaming</p>

            <h1 class="h1 hero-title">
              Create <span class="span">Manage</span> Matches
            </h1>

            <p class="hero-text">
              Find technology or people for digital projects in public sector and Find an individual specialist develope
              researcher.
            </p>

            <button class="btn skewBg">Read More</button>

          </div>

          <figure class="hero-banner img-holder" style="--width: 700; --height: 700;">
            <img src="./assets/images/hero-banner.png" width="700" height="700" alt="hero banner" class="w-100">
          </figure>

        </div>
      </section>





      <!-- 
        - #BRAND
      -->

      <section class="section brand" aria-label="brand">
        <div class="container">

          <ul class="has-scrollbar">

            <li class="brand-item">
              <img src="./assets/images/brand-1.png" width="90" height="90" loading="lazy" alt="brand logo">
            </li>

            <li class="brand-item">
              <img src="./assets/images/brand-2.png" width="90" height="90" loading="lazy" alt="brand logo">
            </li>

            <li class="brand-item">
              <img src="./assets/images/brand-3.png" width="90" height="90" loading="lazy" alt="brand logo">
            </li>

            <li class="brand-item">
              <img src="./assets/images/brand-4.png" width="90" height="90" loading="lazy" alt="brand logo">
            </li>

            <li class="brand-item">
              <img src="./assets/images/brand-5.png" width="90" height="90" loading="lazy" alt="brand logo">
            </li>

            <li class="brand-item">
              <img src="./assets/images/brand-6.png" width="90" height="90" loading="lazy" alt="brand logo">
            </li>

          </ul>

        </div>
      </section>





      <div class="section-wrapper">

        <!-- 
          - #LATEST GAME
        -->

        <section class="section latest-game" aria-label="latest game">
          <div class="container">

            <p class="section-subtitle">Latest Releases</p>

            <h2 class="h2 section-title">
              Create & <span class="span">Manage</span>
            </h2>

            <ul class="has-scrollbar">

              <li class="scrollbar-item">
                <div class="latest-game-card">

                  <figure class="card-banner img-holder" style="--width: 400; --height: 470;">
                    <img src="./assets/images/latest-game-1.jpg" width="400" height="470" loading="lazy"
                      alt="White Walker Daily" class="img-cover">
                  </figure>

                  <div class="card-content">

                    <a href="#" class="card-badge skewBg">Zombie</a>

                    <h3 class="h3">
                      <a href="#" class="card-title">White Walker <span class="span">Daily</span></a>
                    </h3>

                    <p class="card-price">
                      Entry Fee : <span class="span">Free</span>
                    </p>

                  </div>

                </div>
              </li>

              <li class="scrollbar-item">
                <div class="latest-game-card">

                  <figure class="card-banner img-holder" style="--width: 400; --height: 470;">
                    <img src="./assets/images/latest-game-2.jpg" width="400" height="470" loading="lazy"
                      alt="Hunter Killer II" class="img-cover">
                  </figure>

                  <div class="card-content">

                    <a href="#" class="card-badge skewBg">Adventure</a>

                    <h3 class="h3">
                      <a href="#" class="card-title">Hunter Killer <span class="span">II</span></a>
                    </h3>

                    <p class="card-price">
                      Entry Fee : <span class="span">$25.00</span>
                    </p>

                  </div>

                </div>
              </li>

              <li class="scrollbar-item">
                <div class="latest-game-card">

                  <figure class="card-banner img-holder" style="--width: 400; --height: 470;">
                    <img src="./assets/images/latest-game-3.jpg" width="400" height="470" loading="lazy"
                      alt="Cyberpunk Daily" class="img-cover">
                  </figure>

                  <div class="card-content">

                    <a href="#" class="card-badge skewBg">Action</a>

                    <h3 class="h3">
                      <a href="#" class="card-title">Cyberpunk <span class="span">Daily</span></a>
                    </h3>

                    <p class="card-price">
                      Entry Fee : <span class="span">$25.00</span>
                    </p>

                  </div>

                </div>
              </li>

            </ul>

          </div>
        </section>





        <!-- 
          - #LIVE MATCH
        -->

        <section class="section live-match" id="live" aria-label="live match">
          <div class="container">

            <h2 class="h2 section-title">
              Watch Live <span class="span">Match</span>
            </h2>

            <figure class="live-match-banner img-holder" style="--width: 800; --height: 470;">

              <img src="./assets/images/live-match-banner.jpg" width="800" height="470" loading="lazy"
                alt="Live Match Video" class="img-cover">

              <button class="play-btn" aria-label="play video">
                <ion-icon name="play"></ion-icon>
              </button>

            </figure>

            <div class="live-match-player">

              <figure class="player player-1 img-holder" style="--width: 406; --height: 277;">
                <img src="./assets/images/live-match-player-1.png" width="406" height="277" loading="lazy"
                  alt="tokyo eagle" class="w-100">
              </figure>

              <div class="live-match-detail">

                <p class="live-match-subtitle">Upcoming Live Matches</p>

                <time class="live-match-time" datetime="08:30">08:30</time>

              </div>

              <figure class="player player-2 img-holder" style="--width: 400; --height: 305;">
                <img src="./assets/images/live-match-player-2.png" width="400" height="305" loading="lazy"
                  alt="new york hunter7" class="w-100">
              </figure>

            </div>

          </div>
        </section>

      </div>





      <!-- 
        - #FEATURED GAME
      -->

      <section class="section featured-game" id="features" aria-label="featured game">
        <div class="container">

          <h2 class="h2 section-title">
            All Released <span class="span">Games</span>
          </h2>

          <ul class="has-scrollbar">

            <li class="scrollbar-item">
              <div class="featured-game-card">

                <figure class="card-banner img-holder" style="--width: 450; --height: 600;">
                  <img src="./assets/images/featured-game-1.jpg" width="450" height="600" loading="lazy"
                    alt="Just for Gamers" class="img-cover">
                </figure>

                <div class="card-content">

                  <h3 class="h3">
                    <a href="#" class="card-title" tabindex="-1">
                      Just for <span class="span">Gamers</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

                <div class="card-content-overlay">

                  <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt=""
                    class="card-icon">

                  <h3 class="h3">
                    <a href="#" class="card-title">
                      Just for <span class="span">Gamers</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

              </div>
            </li>

            <li class="scrollbar-item">
              <div class="featured-game-card">

                <figure class="card-banner img-holder" style="--width: 450; --height: 600;">
                  <img src="./assets/images/featured-game-2.jpg" width="450" height="600" loading="lazy"
                    alt="Need for Speed" class="img-cover">
                </figure>

                <div class="card-content">

                  <h3 class="h3">
                    <a href="#" class="card-title" tabindex="-1">
                      Need for <span class="span">Speed</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

                <div class="card-content-overlay">

                  <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt=""
                    class="card-icon">

                  <h3 class="h3">
                    <a href="#" class="card-title">
                      Need for <span class="span">Speed</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

              </div>
            </li>

            <li class="scrollbar-item">
              <div class="featured-game-card">

                <figure class="card-banner img-holder" style="--width: 450; --height: 600;">
                  <img src="./assets/images/featured-game-3.jpg" width="450" height="600" loading="lazy"
                    alt="Egypt Hunting Gamers" class="img-cover">
                </figure>

                <div class="card-content">

                  <h3 class="h3">
                    <a href="#" class="card-title" tabindex="-1">
                      Egypt Hunting <span class="span">Gamers</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

                <div class="card-content-overlay">

                  <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt=""
                    class="card-icon">

                  <h3 class="h3">
                    <a href="#" class="card-title">
                      Egypt Hunting <span class="span">Gamers</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

              </div>
            </li>

            <li class="scrollbar-item">
              <div class="featured-game-card">

                <figure class="card-banner img-holder" style="--width: 450; --height: 600;">
                  <img src="./assets/images/featured-game-4.jpg" width="450" height="600" loading="lazy"
                    alt="Just for Gamers" class="img-cover">
                </figure>

                <div class="card-content">

                  <h3 class="h3">
                    <a href="#" class="card-title" tabindex="-1">
                      Just for <span class="span">Gamers</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

                <div class="card-content-overlay">

                  <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt=""
                    class="card-icon">

                  <h3 class="h3">
                    <a href="#" class="card-title">
                      Just for <span class="span">Gamers</span>
                    </a>
                  </h3>

                  <span class="card-meta">
                    <ion-icon name="notifications"></ion-icon>

                    <span class="span">Playstation 5, Xbox</span>
                  </span>

                </div>

              </div>
            </li>

          </ul>

        </div>
      </section>





      <!-- 
        - #SHOP
      -->

      <section class="section shop" id="shop" aria-label="shop"
        style="background-image: url('./assets/images/shop-bg.jpg')">
        <div class="container">

          <h2 class="h2 section-title">
            Gaming Product <span class="span">Corner</span>
          </h2>

          <p class="section-text">
            Compete with 100 players on a remote island for winner takes showdown known issue where certain skin
            strategic
          </p>

          <ul class="has-scrollbar">

            <li class="scrollbar-item">
              <div class="shop-card">

                <figure class="card-banner img-holder" style="--width: 300; --height: 260;">
                  <img src="./assets/images/shop-img-1.jpg" width="300" height="260" loading="lazy"
                    alt="Women Black T-Shirt" class="img-cover">
                </figure>

                <div class="card-content">

                  <a href="#" class="card-badge skewBg">t-shirt</a>

                  <h3 class="h3">
                    <a href="#" class="card-title">Women Black T-Shirt</a>
                  </h3>

                  <div class="card-wrapper">
                    <p class="card-price">$29.00</p>

                    <button class="card-btn">
                      <ion-icon name="basket"></ion-icon>
                    </button>
                  </div>

                </div>

              </div>
            </li>

            <li class="scrollbar-item">
              <div class="shop-card">

                <figure class="card-banner img-holder" style="--width: 300; --height: 260;">
                  <img src="./assets/images/shop-img-2.jpg" width="300" height="260" loading="lazy"
                    alt="Gears 5 Xbox Controller" class="img-cover">
                </figure>

                <div class="card-content">

                  <a href="#" class="card-badge skewBg">x-box</a>

                  <h3 class="h3">
                    <a href="#" class="card-title">Gears 5 Xbox Controller</a>
                  </h3>

                  <div class="card-wrapper">
                    <p class="card-price">$29.00</p>

                    <button class="card-btn">
                      <ion-icon name="basket"></ion-icon>
                    </button>
                  </div>

                </div>

              </div>
            </li>

            <li class="scrollbar-item">
              <div class="shop-card">

                <figure class="card-banner img-holder" style="--width: 300; --height: 260;">
                  <img src="./assets/images/shop-img-3.jpg" width="300" height="260" loading="lazy"
                    alt="GeForce RTX 2070" class="img-cover">
                </figure>

                <div class="card-content">

                  <a href="#" class="card-badge skewBg">Graphics</a>

                  <h3 class="h3">
                    <a href="#" class="card-title">GeForce RTX 2070</a>
                  </h3>

                  <div class="card-wrapper">
                    <p class="card-price">$29.00</p>

                    <button class="card-btn">
                      <ion-icon name="basket"></ion-icon>
                    </button>
                  </div>

                </div>

              </div>
            </li>

            <li class="scrollbar-item">
              <div class="shop-card">

                <figure class="card-banner img-holder" style="--width: 300; --height: 260;">
                  <img src="./assets/images/shop-img-4.jpg" width="300" height="260" loading="lazy"
                    alt="Virtual Reality Smiled" class="img-cover">
                </figure>

                <div class="card-content">

                  <a href="#" class="card-badge skewBg">VR-Box</a>

                  <h3 class="h3">
                    <a href="#" class="card-title">Virtual Reality Smiled</a>
                  </h3>

                  <div class="card-wrapper">
                    <p class="card-price">$29.00</p>

                    <button class="card-btn">
                      <ion-icon name="basket"></ion-icon>
                    </button>
                  </div>

                </div>

              </div>
            </li>

          </ul>

        </div>
      </section>





      <!-- 
        - #BLOG
      -->

      <section class="section blog" id="blog" aria-label="blog">
        <div class="container">

          <h2 class="h2 section-title">
            Latest News & <span class="span">Articles</span>
          </h2>

          <p class="section-text">
            Compete With 100 Players On A Remote Island For Winner Takes Showdown Known Issue Where Certain Skin
            Strategic
          </p>

          <ul class="blog-list">

            <li>
              <div class="blog-card">

                <figure class="card-banner img-holder" style="--width: 400; --height: 290;">
                  <img src="./assets/images/blog-1.jpg" width="400" height="290" loading="lazy"
                    alt="Shooter Action Video" class="img-cover">
                </figure>

                <div class="card-content">

                  <ul class="card-meta-list">

                    <li class="card-meta-item">
                      <ion-icon name="person-outline"></ion-icon>

                      <a href="#" class="item-text">Admin</a>
                    </li>

                    <li class="card-meta-item">
                      <ion-icon name="calendar-outline"></ion-icon>

                      <time datetime="2022-09-19" class="item-text">September 19, 2022</time>
                    </li>

                  </ul>

                  <h3>
                    <a href="#" class="card-title">Shooter Action Video</a>
                  </h3>

                  <p class="card-text">
                    Compete With 100 Players On A Remote Island Thats Winner Takes Showdown Known Issue.
                  </p>

                  <a href="#" class="card-link">
                    <span class="span">Read More</span>

                    <ion-icon name="caret-forward"></ion-icon>
                  </a>

                </div>

              </div>
            </li>

            <li>
              <div class="blog-card">

                <figure class="card-banner img-holder" style="--width: 400; --height: 290;">
                  <img src="./assets/images/blog-2.jpg" width="400" height="290" loading="lazy" alt="The Walking Dead"
                    class="img-cover">
                </figure>

                <div class="card-content">

                  <ul class="card-meta-list">

                    <li class="card-meta-item">
                      <ion-icon name="person-outline"></ion-icon>

                      <a href="#" class="item-text">Admin</a>
                    </li>

                    <li class="card-meta-item">
                      <ion-icon name="calendar-outline"></ion-icon>

                      <time datetime="2022-09-19" class="item-text">September 19, 2022</time>
                    </li>

                  </ul>

                  <h3>
                    <a href="#" class="card-title">The Walking Dead</a>
                  </h3>

                  <p class="card-text">
                    Compete With 100 Players On A Remote Island Thats Winner Takes Showdown Known Issue.
                  </p>

                  <a href="#" class="card-link">
                    <span class="span">Read More</span>

                    <ion-icon name="caret-forward"></ion-icon>
                  </a>

                </div>

              </div>
            </li>

            <li>
              <div class="blog-card">

                <figure class="card-banner img-holder" style="--width: 400; --height: 290;">
                  <img src="./assets/images/blog-3.jpg" width="400" height="290" loading="lazy"
                    alt="Defense Of The Ancients" class="img-cover">
                </figure>

                <div class="card-content">

                  <ul class="card-meta-list">

                    <li class="card-meta-item">
                      <ion-icon name="person-outline"></ion-icon>

                      <a href="#" class="item-text">Admin</a>
                    </li>

                    <li class="card-meta-item">
                      <ion-icon name="calendar-outline"></ion-icon>

                      <time datetime="2022-09-19" class="item-text">September 19, 2022</time>
                    </li>

                  </ul>

                  <h3>
                    <a href="#" class="card-title">Defense Of The Ancients</a>
                  </h3>

                  <p class="card-text">
                    Compete With 100 Players On A Remote Island Thats Winner Takes Showdown Known Issue.
                  </p>

                  <a href="#" class="card-link">
                    <span class="span">Read More</span>

                    <ion-icon name="caret-forward"></ion-icon>
                  </a>

                </div>

              </div>
            </li>

          </ul>

        </div>
      </section>





      <!-- 
        - #NEWSLETTER
      -->

      <section class="newsletter" aria-label="newsletter">
        <div class="container">

          <div class="newsletter-card">

            <h2 class="h2">
              Our <span class="span">Newsletter</span>
            </h2>

            <form action="" class="newsletter-form">

              <div class="input-wrapper skewBg">
                <input type="email" name="email_address" aria-label="email" placeholder="Enter your email..." required
                  class="email-field">

                <ion-icon name="mail-outline"></ion-icon>
              </div>

              <button type="submit" class="btn newsletter-btn skewBg">
                <span class="span">Subscribe</span>

                <ion-icon name="paper-plane" aria-hidden="true"></ion-icon>
              </button>

            </form>

          </div>

        </div>
      </section>

    </article>
  </main>





  <!-- 
    - #FOOTER
  -->

  <footer class="footer">

    <div class="footer-top">
      <div class="container">

        <div class="footer-brand">

          <a href="#" class="logo">Gamics</a>

          <p class="footer-text">
            Gamics marketplace the relase etras thats sheets continig passag.
          </p>

          <ul class="contact-list">

            <li class="contact-item">
              <div class="contact-icon">
                <ion-icon name="location"></ion-icon>
              </div>

              <address class="item-text">
                Address : PO Box W75 Street lan West new queens
              </address>
            </li>

            <li class="contact-item">
              <div class="contact-icon">
                <ion-icon name="headset"></ion-icon>
              </div>

              <a href="tel:+241245654235" class="item-text">Phone : +24 1245 654 235</a>
            </li>

            <li class="contact-item">
              <div class="contact-icon">
                <ion-icon name="mail-open"></ion-icon>
              </div>

              <a href="mailto:info@exemple.com" class="item-text">Email : info@exemple.com</a>
            </li>

          </ul>

        </div>

        <ul class="footer-list">

          <li>
            <p class="footer-list-title">Products</p>
          </li>

          <li>
            <a href="#" class="footer-link">Graphics (26)</a>
          </li>

          <li>
            <a href="#" class="footer-link">Backgrounds (11)</a>
          </li>

          <li>
            <a href="#" class="footer-link">Fonts (9)</a>
          </li>

          <li>
            <a href="#" class="footer-link">Music (3)</a>
          </li>

          <li>
            <a href="#" class="footer-link">Photography (3)</a>
          </li>

        </ul>

        <ul class="footer-list">

          <li>
            <p class="footer-list-title">Need Help?</p>
          </li>

          <li>
            <a href="#" class="footer-link">Terms & Conditions</a>
          </li>

          <li>
            <a href="#" class="footer-link">Privacy Policy</a>
          </li>

          <li>
            <a href="#" class="footer-link">Refund Policy</a>
          </li>

          <li>
            <a href="#" class="footer-link">Affiliate</a>
          </li>

          <li>
            <a href="#" class="footer-link">Use Cases</a>
          </li>

        </ul>

        <div class="footer-wrapper">

          <div class="social-wrapper">

            <p class="footer-list-title">Follow Us</p>

            <ul class="social-list">

              <li>
                <a href="#" class="social-link" style="background-color: #3b5998">
                  <ion-icon name="logo-facebook"></ion-icon>
                </a>
              </li>

              <li>
                <a href="#" class="social-link" style="background-color: #55acee">
                  <ion-icon name="logo-twitter"></ion-icon>
                </a>
              </li>

              <li>
                <a href="#" class="social-link" style="background-color: #d71e18">
                  <ion-icon name="logo-pinterest"></ion-icon>
                </a>
              </li>

              <li>
                <a href="#" class="social-link" style="background-color: #1565c0">
                  <ion-icon name="logo-linkedin"></ion-icon>
                </a>
              </li>

            </ul>

          </div>

          <div class="footer-newsletter">

            <p class="footer-list-title">Newsletter Sign Up</p>

            <form action="" class="footer-newsletter">
              <input type="email" name="email_address" aria-label="email" placeholder="Enter your email" required
                class="email-field">

              <button type="submit" class="footer-btn" aria-label="submit">
                <ion-icon name="rocket"></ion-icon>
              </button>
            </form>

          </div>

        </div>

      </div>
    </div>

    <div class="footer-bottom">
      <div class="container">

        <p class="copyright">
          &copy; 2022 Gamics. All Right Reserved by <a href="#" class="copyright-link">codewithsadee</a>
        </p>

        <img src="./assets/images/footer-bottom-img.png" width="340" height="21" loading="lazy" alt=""
          class="footer-bottom-img">

      </div>
    </div>

  </footer>





  <!-- 
    - #BACK TO TOP
  -->

  <a href="#top" class="back-top-btn" aria-label="back to top" data-back-top-btn>
    <ion-icon name="caret-up"></ion-icon>
  </a>





  <!-- 
    - custom js link
  -->
  <script src="./assets/js/script.js" defer></script>

  <!-- 
    - ionicon link
  -->
  <script type="module" src="https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.esm.js"></script>
  <script nomodule src="https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.js"></script>

</body>

</html>
 297 changes: 297 additions & 0 deletions297  
Gamics/index.txt
@@ -0,0 +1,297 @@
Gamics - Create Manage Matches



#---------- HEDER ----------#

Exclusive Black Friday ! Offer 
10 
Days

Follow us on :

<ion-icon name="logo-facebook"></ion-icon>
<ion-icon name="logo-twitter"></ion-icon>
<ion-icon name="logo-pinterest"></ion-icon>
<ion-icon name="logo-linkedin"></ion-icon>

Gamics

Home
Live
Features
Shop
Blog
Contact

aria-label = cart

<ion-icon name="cart"></ion-icon>
0

aria-label = open search

<ion-icon name="search-outline"></ion-icon>

aria-label = toggle menu
<ion-icon name="menu-outline" class="menu"></ion-icon>
<ion-icon name="close-outline" class="close"></ion-icon>



#---------- SEARCH BOX ----------#

aria-label = search

placeholder = Search here...

aria-label = submit search
<ion-icon name="search-outline"></ion-icon>

aria-label = close search



#---------- HERO ----------#

World Gaming

Create Manage Matches

Find technology or people for digital projects in public sector and Find an individual specialist develope researcher.

Read More

alt = hero banner



#---------- BRAND ----------#

alt = brand logo



#---------- LATEST GAME ----------#

Latest Releases

Create & Manage

alt = White Walker Daily

Zombie

White Walker
Daily

Entry Fee :
Free

alt = Hunter Killer II

Adventure

Hunter Killer
II

Entry Fee : 
$25.00

alt = Cyberpunk Daily

Action

Cyberpunk
Daily



#---------- LIVE MATCH ----------#

Watch Live 
Match

alt = Live Match Video

aria-label = play video
<ion-icon name="play"></ion-icon>

alt = tokyo eagle

Upcoming Live Matches

08:30

alt = new york hunter7



#---------- FEATURED GAME ----------#

All Released
Games

alt = Just for Gamers

Just for
Gamers

<ion-icon name="notifications"></ion-icon>

Playstation 5, Xbox

alt = Need for Speed

Need for
Speed

alt = Egypt Hunting Gamers

Egypt Hunting
Gamers

alt = Just for Gamers

Just for
Gamers



#---------- SHOP ----------#

Gaming Product 
Corner

Compete with 100 players on a remote island for winner takes showdown known issue where certain skin strategic

alt = Women Black T-Shirt

t-shirt

Women Black T-Shirt

$29.00

<ion-icon name="basket"></ion-icon>


alt = Gears 5 Xbox Controller

x-box

Gears 5 Xbox Controller


alt = GeForce RTX 2070

Graphics

GeForce RTX 2070


alt = Virtual Reality Smiled

VR-Box

Virtual Reality Smiled



#---------- BLOG ----------#

Latest News &
Articles

Compete With 100 Players On A Remote Island For Winner Takes Showdown Known Issue Where Certain Skin Strategic

alt = Shooter Action Video

<ion-icon name="person-outline"></ion-icon>
Admin

<ion-icon name="calendar-outline"></ion-icon>
September 19, 2022

Shooter Action Video

Compete With 100 Players On A Remote Island Thats Winner Takes Showdown Known Issue.

Read More

<ion-icon name="caret-forward"></ion-icon>

alt = The Walking Dead

alt = Defense Of The Ancients



#---------- NEWSLETTER ----------#

Our
Newsletter

placeholder = Enter your email...

<ion-icon name="mail-outline"></ion-icon>

Subscribe
<ion-icon name="paper-plane" aria-hidden="true"></ion-icon>



#---------- FOOTER ----------#

Gamics

Gamics marketplace the relase etras thats sheets continig passag.

<ion-icon name="location"></ion-icon>
Address : PO Box W75 Street lan West new queens

<ion-icon name="headset"></ion-icon>
Phone : +24 1245 654 235

<ion-icon name="mail-open"></ion-icon>
Email : info@exemple.com

Products

Graphics (26)
Backgrounds (11)
Fonts (9)
Music (3)
Photography (3)

Need Help?

Terms & Conditions
Privacy Policy
Refund Policy
Affiliate
Use Cases

Follow Us

<ion-icon name="logo-facebook"></ion-icon>
<ion-icon name="logo-twitter"></ion-icon>
<ion-icon name="logo-pinterest"></ion-icon>
<ion-icon name="logo-linkedin"></ion-icon>

Newsletter Sign Up

placeholder = Enter your email

aria-label = submit
<ion-icon name="rocket"></ion-icon>

&copy; 2022 Gamics. All Right Reserved by codewithsadee



#---------- BACK TO TOP ----------#

aria-label = back to top

<ion-icon name="caret-up"></ion-icon>
 104 changes: 104 additions & 0 deletions104  
Gamics/style-guide.md
@@ -0,0 +1,104 @@
# Essential Stuff

## Html import links

Google font

``` html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link
  href="https://fonts.googleapis.com/css2?family=Oxanium:wght@600;700;800&family=Poppins:wght@400;500;600;700;800;900&display=swap"
  rel="stylesheet">
```

Ionicon

``` html
<script type="module" src="https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.esm.js"></script>
<script nomodule src="https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.js"></script>
```

---

## Colors

``` css
--rich-black-fogra-29_95: hsla(222, 18%, 11%, 0.95);
--raisin-black-1: hsl(0, 0%, 16%);
--raisin-black-2: hsl(236, 17%, 17%);
--raisin-black-3: hsl(280, 11%, 11%);
--raisin-black-4: hsl(280, 8%, 15%);
--english-violet: hsl(274, 21%, 23%);
--eerie-black-1: hsl(277, 25%, 10%);
--eerie-black-2: hsl(280, 7%, 8%);
--roman-silver: hsl(220, 6%, 59%);
--quick-silver: hsl(0, 1%, 65%);
--light-gray-1: hsl(0, 0%, 80%);
--light-gray-2: hsl(0, 2%, 82%);
--marigold_75: hsla(42, 99%, 46%, 0.75);
--xiketic_90: hsla(280, 37%, 8%, 0.9);
--cultured-2: hsl(0, 0%, 97%);
--marigold: hsl(42, 99%, 46%);
--platinum: hsl(0, 0%, 89%);
--dim-gray: hsl(0, 0%, 42%);
--white_15: hsla(0, 0%, 100%, 0.15);
--white_10: hsla(0, 0%, 100%, 0.1);
--xiketic: hsl(277, 25%, 10%);
--silver: hsl(0, 0%, 78%);
--white: hsl(0, 0%, 100%);
--jet: hsl(236, 13%, 23%);
```

## Typography

``` css
--ff-oxanium: 'Oxanium', cursive;
--ff-poppins: 'Poppins', sans-serif;

--fs-1: 7rem;
--fs-2: 4.5rem;
--fs-3: 3.6rem;
--fs-4: 2.4rem;
--fs-5: 2.2rem;
--fs-6: 2rem;
--fs-7: 1.6rem;
--fs-8: 1.5rem;
--fs-9: 1.4rem;
--fs-10: 1.3rem;
--fs-11: 1.2rem;

--fw-500: 500;
--fw-600: 600;
--fw-700: 700;
--fw-800: 800;
```

## Spacing

``` css
--section-padding: 120px;
```

## Gradient

``` css
--gradient: radial-gradient(circle, hsl(250, 7%, 17%), hsl(250, 11%, 11%));
```

## Shadow

``` css
--shadow-1: 0px 2px 8px 0px hsla(0, 0%, 0%, 0.2),
            inset 0px 2px 8px 0px hsla(0, 0%, 0%, 0.4);
--shadow-2: 0px 5px 10px 1px hsla(0, 0%, 0%, 0.4);
--shadow-3: 0px 5px 10px 1px hsla(219, 98%, 17%, 0.2);
--shadow-4: 0px 5px 10px 1px hsla(0, 0%, 0%, 0.15);
```

## Transition

``` css
--transition: 0.25s ease;
--cubic-out: cubic-bezier(0.33, 0.85, 0.4, 0.96);
```
0 comments on commit 56315e2
Please sign in to comment.
Footer
© 2023 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
@@ -0,0 +1,1165 @@ <!DOCTYPE html> <html lang="en"> <head> <meta charset="UTF-8"> <meta http-equiv="X-UA-Compatible" content="IE=edge"> <meta name="viewport" content="width=device-width, initial-scale=1.0"> <title>Gamics - Create Manage Matches</title> <!-- - favicon --> <link rel="shortcut icon" href="./favicon.svg" type="image/svg+xml"> <!-- - custom css link --> <link rel="stylesheet" href="./assets/css/style.css"> <!-- - google font link --> <link rel="preconnect" href="https://fonts.googleapis.com"> <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin> <link href="https://fonts.googleapis.com/css2?family=Oxanium:wght@600;700;800&family=Poppins:wght@400;500;600;700;800;900&display=swap" rel="stylesheet"> <!-- - preload images --> </head> <body id="top"> <!-- - #HEADER --> <header class="header"> <div class="header-top"> <div class="container"> <div class="countdown-text"> Exclusive Black Friday ! Offer <span class="span skewBg">10</span> Days </div> <div class="social-wrapper"> <p class="social-title">Follow us on :</p> <ul class="social-list"> <li> <a href="#" class="social-link"> <ion-icon name="logo-facebook"></ion-icon> </a> </li> <li> <a href="#" class="social-link"> <ion-icon name="logo-twitter"></ion-icon> </a> </li> <li> <a href="#" class="social-link"> <ion-icon name="logo-pinterest"></ion-icon> </a> </li> <li> <a href="#" class="social-link"> <ion-icon name="logo-linkedin"></ion-icon> </a> </li> </ul> </div> </div> </div> <div class="header-bottom skewBg" data-header> <div class="container"> <a href="#" class="logo">Gamics</a> <nav class="navbar" data-navbar> <ul class="navbar-list"> <li class="navbar-item"> <a href="#home" class="navbar-link skewBg" data-nav-link>Home</a> </li> <li class="navbar-item"> <a href="#live" class="navbar-link skewBg" data-nav-link>Live</a> </li> <li class="navbar-item"> <a href="#features" class="navbar-link skewBg" data-nav-link>Features</a> </li> <li class="navbar-item"> <a href="#shop" class="navbar-link skewBg" data-nav-link>Shop</a> </li> <li class="navbar-item"> <a href="#blog" class="navbar-link skewBg" data-nav-link>Blog</a> </li> <li class="navbar-item"> <a href="#" class="navbar-link skewBg" data-nav-link>Contact</a> </li> </ul> </nav> <div class="header-actions"> <button class="cart-btn" aria-label="cart"> <ion-icon name="cart"></ion-icon> <span class="cart-badge">0</span> </button> <button class="search-btn" aria-label="open search" data-search-toggler> <ion-icon name="search-outline"></ion-icon> </button> <button class="nav-toggle-btn" aria-label="toggle menu" data-nav-toggler> <ion-icon name="menu-outline" class="menu"></ion-icon> <ion-icon name="close-outline" class="close"></ion-icon> </button> </div> </div> </div> </header> <!-- - #SEARCH BOX --> <div class="search-container" data-search-box> <div class="input-wrapper"> <input type="search" name="search" aria-label="search" placeholder="Search here..." class="search-field"> <button class="search-submit" aria-label="submit search" data-search-toggler> <ion-icon name="search-outline"></ion-icon> </button> <button class="search-close" aria-label="close search" data-search-toggler></button> </div> </div> <main> <article> <!-- - #HERO --> <section class="section hero" id="home" aria-label="home" style="background-image: url('./assets/images/hero-bg.jpg')"> <div class="container"> <div class="hero-content"> <p class="hero-subtitle">World Gaming</p> <h1 class="h1 hero-title"> Create <span class="span">Manage</span> Matches </h1> <p class="hero-text"> Find technology or people for digital projects in public sector and Find an individual specialist develope researcher. </p> <button class="btn skewBg">Read More</button> </div> <figure class="hero-banner img-holder" style="--width: 700; --height: 700;"> <img src="./assets/images/hero-banner.png" width="700" height="700" alt="hero banner" class="w-100"> </figure> </div> </section> <!-- - #BRAND --> <section class="section brand" aria-label="brand"> <div class="container"> <ul class="has-scrollbar"> <li class="brand-item"> <img src="./assets/images/brand-1.png" width="90" height="90" loading="lazy" alt="brand logo"> </li> <li class="brand-item"> <img src="./assets/images/brand-2.png" width="90" height="90" loading="lazy" alt="brand logo"> </li> <li class="brand-item"> <img src="./assets/images/brand-3.png" width="90" height="90" loading="lazy" alt="brand logo"> </li> <li class="brand-item"> <img src="./assets/images/brand-4.png" width="90" height="90" loading="lazy" alt="brand logo"> </li> <li class="brand-item"> <img src="./assets/images/brand-5.png" width="90" height="90" loading="lazy" alt="brand logo"> </li> <li class="brand-item"> <img src="./assets/images/brand-6.png" width="90" height="90" loading="lazy" alt="brand logo"> </li> </ul> </div> </section> <div class="section-wrapper"> <!-- - #LATEST GAME --> <section class="section latest-game" aria-label="latest game"> <div class="container"> <p class="section-subtitle">Latest Releases</p> <h2 class="h2 section-title"> Create & <span class="span">Manage</span> </h2> <ul class="has-scrollbar"> <li class="scrollbar-item"> <div class="latest-game-card"> <figure class="card-banner img-holder" style="--width: 400; --height: 470;"> <img src="./assets/images/latest-game-1.jpg" width="400" height="470" loading="lazy" alt="White Walker Daily" class="img-cover"> </figure> <div class="card-content"> <a href="#" class="card-badge skewBg">Zombie</a> <h3 class="h3"> <a href="#" class="card-title">White Walker <span class="span">Daily</span></a> </h3> <p class="card-price"> Entry Fee : <span class="span">Free</span> </p> </div> </div> </li> <li class="scrollbar-item"> <div class="latest-game-card"> <figure class="card-banner img-holder" style="--width: 400; --height: 470;"> <img src="./assets/images/latest-game-2.jpg" width="400" height="470" loading="lazy" alt="Hunter Killer II" class="img-cover"> </figure> <div class="card-content"> <a href="#" class="card-badge skewBg">Adventure</a> <h3 class="h3"> <a href="#" class="card-title">Hunter Killer <span class="span">II</span></a> </h3> <p class="card-price"> Entry Fee : <span class="span">$25.00</span> </p> </div> </div> </li> <li class="scrollbar-item"> <div class="latest-game-card"> <figure class="card-banner img-holder" style="--width: 400; --height: 470;"> <img src="./assets/images/latest-game-3.jpg" width="400" height="470" loading="lazy" alt="Cyberpunk Daily" class="img-cover"> </figure> <div class="card-content"> <a href="#" class="card-badge skewBg">Action</a> <h3 class="h3"> <a href="#" class="card-title">Cyberpunk <span class="span">Daily</span></a> </h3> <p class="card-price"> Entry Fee : <span class="span">$25.00</span> </p> </div> </div> </li> </ul> </div> </section> <!-- - #LIVE MATCH --> <section class="section live-match" id="live" aria-label="live match"> <div class="container"> <h2 class="h2 section-title"> Watch Live <span class="span">Match</span> </h2> <figure class="live-match-banner img-holder" style="--width: 800; --height: 470;"> <img src="./assets/images/live-match-banner.jpg" width="800" height="470" loading="lazy" alt="Live Match Video" class="img-cover"> <button class="play-btn" aria-label="play video"> <ion-icon name="play"></ion-icon> </button> </figure> <div class="live-match-player"> <figure class="player player-1 img-holder" style="--width: 406; --height: 277;"> <img src="./assets/images/live-match-player-1.png" width="406" height="277" loading="lazy" alt="tokyo eagle" class="w-100"> </figure> <div class="live-match-detail"> <p class="live-match-subtitle">Upcoming Live Matches</p> <time class="live-match-time" datetime="08:30">08:30</time> </div> <figure class="player player-2 img-holder" style="--width: 400; --height: 305;"> <img src="./assets/images/live-match-player-2.png" width="400" height="305" loading="lazy" alt="new york hunter7" class="w-100"> </figure> </div> </div> </section> </div> <!-- - #FEATURED GAME --> <section class="section featured-game" id="features" aria-label="featured game"> <div class="container"> <h2 class="h2 section-title"> All Released <span class="span">Games</span> </h2> <ul class="has-scrollbar"> <li class="scrollbar-item"> <div class="featured-game-card"> <figure class="card-banner img-holder" style="--width: 450; --height: 600;"> <img src="./assets/images/featured-game-1.jpg" width="450" height="600" loading="lazy" alt="Just for Gamers" class="img-cover"> </figure> <div class="card-content"> <h3 class="h3"> <a href="#" class="card-title" tabindex="-1"> Just for <span class="span">Gamers</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> <div class="card-content-overlay"> <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt="" class="card-icon"> <h3 class="h3"> <a href="#" class="card-title"> Just for <span class="span">Gamers</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> </div> </li> <li class="scrollbar-item"> <div class="featured-game-card"> <figure class="card-banner img-holder" style="--width: 450; --height: 600;"> <img src="./assets/images/featured-game-2.jpg" width="450" height="600" loading="lazy" alt="Need for Speed" class="img-cover"> </figure> <div class="card-content"> <h3 class="h3"> <a href="#" class="card-title" tabindex="-1"> Need for <span class="span">Speed</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> <div class="card-content-overlay"> <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt="" class="card-icon"> <h3 class="h3"> <a href="#" class="card-title"> Need for <span class="span">Speed</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> </div> </li> <li class="scrollbar-item"> <div class="featured-game-card"> <figure class="card-banner img-holder" style="--width: 450; --height: 600;"> <img src="./assets/images/featured-game-3.jpg" width="450" height="600" loading="lazy" alt="Egypt Hunting Gamers" class="img-cover"> </figure> <div class="card-content"> <h3 class="h3"> <a href="#" class="card-title" tabindex="-1"> Egypt Hunting <span class="span">Gamers</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> <div class="card-content-overlay"> <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt="" class="card-icon"> <h3 class="h3"> <a href="#" class="card-title"> Egypt Hunting <span class="span">Gamers</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> </div> </li> <li class="scrollbar-item"> <div class="featured-game-card"> <figure class="card-banner img-holder" style="--width: 450; --height: 600;"> <img src="./assets/images/featured-game-4.jpg" width="450" height="600" loading="lazy" alt="Just for Gamers" class="img-cover"> </figure> <div class="card-content"> <h3 class="h3"> <a href="#" class="card-title" tabindex="-1"> Just for <span class="span">Gamers</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> <div class="card-content-overlay"> <img src="./assets/images/featured-game-icon.png" width="36" height="61" loading="lazy" alt="" class="card-icon"> <h3 class="h3"> <a href="#" class="card-title"> Just for <span class="span">Gamers</span> </a> </h3> <span class="card-meta"> <ion-icon name="notifications"></ion-icon> <span class="span">Playstation 5, Xbox</span> </span> </div> </div> </li> </ul> </div> </section> <!-- - #SHOP --> <section class="section shop" id="shop" aria-label="shop" style="background-image: url('./assets/images/shop-bg.jpg')"> <div class="container"> <h2 class="h2 section-title"> Gaming Product <span class="span">Corner</span> </h2> <p class="section-text"> Compete with 100 players on a remote island for winner takes showdown known issue where certain skin strategic </p> <ul class="has-scrollbar"> <li class="scrollbar-item"> <div class="shop-card"> <figure class="card-banner img-holder" style="--width: 300; --height: 260;"> <img src="./assets/images/shop-img-1.jpg" width="300" height="260" loading="lazy" alt="Women Black T-Shirt" class="img-cover"> </figure> <div class="card-content"> <a href="#" class="card-badge skewBg">t-shirt</a> <h3 class="h3"> <a href="#" class="card-title">Women Black T-Shirt</a> </h3> <div class="card-wrapper"> <p class="card-price">$29.00</p> <button class="card-btn"> <ion-icon name="basket"></ion-icon> </button> </div> </div> </div> </li> <li class="scrollbar-item"> <div class="shop-card"> <figure class="card-banner img-holder" style="--width: 300; --height: 260;"> <img src="./assets/images/shop-img-2.jpg" width="300" height="260" loading="lazy" alt="Gears 5 Xbox Controller" class="img-cover"> </figure> <div class="card-content"> <a href="#" class="card-badge skewBg">x-box</a> <h3 class="h3"> <a href="#" class="card-title">Gears 5 Xbox Controller</a> </h3> <div class="card-wrapper"> <p class="card-price">$29.00</p> <button class="card-btn"> <ion-icon name="basket"></ion-icon> </button> </div> </div> </div> </li> <li class="scrollbar-item"> <div class="shop-card"> <figure class="card-banner img-holder" style="--width: 300; --height: 260;"> <img src="./assets/images/shop-img-3.jpg" width="300" height="260" loading="lazy" alt="GeForce RTX 2070" class="img-cover"> </figure> <div class="card-content"> <a href="#" class="card-badge skewBg">Graphics</a> <h3 class="h3"> <a href="#" class="card-title">GeForce RTX 2070</a> </h3> <div class="card-wrapper"> <p class="card-price">$29.00</p> <button class="card-btn"> <ion-icon name="basket"></ion-icon> </button> </div> </div> </div> </li> <li class="scrollbar-item"> <div class="shop-card"> <figure class="card-banner img-holder" style="--width: 300; --height: 260;"> <img src="./assets/images/shop-img-4.jpg" width="300" height="260" loading="lazy" alt="Virtual Reality Smiled" class="img-cover"> </figure> <div class="card-content"> <a href="#" class="card-badge skewBg">VR-Box</a> <h3 class="h3"> <a href="#" class="card-title">Virtual Reality Smiled</a> </h3> <div class="card-wrapper"> <p class="card-price">$29.00</p> <button class="card-btn"> <ion-icon name="basket"></ion-icon> </button> </div> </div> </div> </li> </ul> </div> </section> <!-- - #BLOG --> <section class="section blog" id="blog" aria-label="blog"> <div class="container"> <h2 class="h2 section-title"> Latest News & <span class="span">Articles</span> </h2> <p class="section-text"> Compete With 100 Players On A Remote Island For Winner Takes Showdown Known Issue Where Certain Skin Strategic </p> <ul class="blog-list"> <li> <div class="blog-card"> <figure class="card-banner img-holder" style="--width: 400; --height: 290;"> <img src="./assets/images/blog-1.jpg" width="400" height="290" loading="lazy" alt="Shooter Action Video" class="img-cover"> </figure> <div class="card-content"> <ul class="card-meta-list"> <li class="card-meta-item"> <ion-icon name="person-outline"></ion-icon> <a href="#" class="item-text">Admin</a> </li> <li class="card-meta-item"> <ion-icon name="calendar-outline"></ion-icon> <time datetime="2022-09-19" class="item-text">September 19, 2022</time> </li> </ul> <h3> <a href="#" class="card-title">Shooter Action Video</a> </h3> <p class="card-text"> Compete With 100 Players On A Remote Island Thats Winner Takes Showdown Known Issue. </p> <a href="#" class="card-link"> <span class="span">Read More</span> <ion-icon name="caret-forward"></ion-icon> </a> </div> </div> </li> <li> <div class="blog-card"> <figure class="card-banner img-holder" style="--width: 400; --height: 290;"> <img src="./assets/images/blog-2.jpg" width="400" height="290" loading="lazy" alt="The Walking Dead" class="img-cover"> </figure> <div class="card-content"> <ul class="card-meta-list"> <li class="card-meta-item"> <ion-icon name="person-outline"></ion-icon> <a href="#" class="item-text">Admin</a> </li> <li class="card-meta-item"> <ion-icon name="calendar-outline"></ion-icon> <time datetime="2022-09-19" class="item-text">September 19, 2022</time> </li> </ul> <h3> <a href="#" class="card-title">The Walking Dead</a> </h3> <p class="card-text"> Compete With 100 Players On A Remote Island Thats Winner Takes Showdown Known Issue. </p> <a href="#" class="card-link"> <span class="span">Read More</span> <ion-icon name="caret-forward"></ion-icon> </a> </div> </div> </li> <li> <div class="blog-card"> <figure class="card-banner img-holder" style="--width: 400; --height: 290;"> <img src="./assets/images/blog-3.jpg" width="400" height="290" loading="lazy" alt="Defense Of The Ancients" class="img-cover"> </figure> <div class="card-content"> <ul class="card-meta-list"> <li class="card-meta-item"> <ion-icon name="person-outline"></ion-icon> <a href="#" class="item-text">Admin</a> </li> <li class="card-meta-item"> <ion-icon name="calendar-outline"></ion-icon> <time datetime="2022-09-19" class="item-text">September 19, 2022</time> </li> </ul> <h3> <a href="#" class="card-title">Defense Of The Ancients</a> </h3> <p class="card-text"> Compete With 100 Players On A Remote Island Thats Winner Takes Showdown Known Issue. </p> <a href="#" class="card-link"> <span class="span">Read More</span> <ion-icon name="caret-forward"></ion-icon> </a> </div> </div> </li> </ul> </div> </section> <!-- - #NEWSLETTER --> <section class="newsletter" aria-label="newsletter"> <div class="container"> <div class="newsletter-card"> <h2 class="h2"> Our <span class="span">Newsletter</span> </h2> <form action="" class="newsletter-form"> <div class="input-wrapper skewBg"> <input type="email" name="email_address" aria-label="email" placeholder="Enter your email..." required class="email-field"> <ion-icon name="mail-outline"></ion-icon> </div> <button type="submit" class="btn newsletter-btn skewBg"> <span class="span">Subscribe</span> <ion-icon name="paper-plane" aria-hidden="true"></ion-icon> </button> </form> </div> </div> </section> </article> </main> <!-- - #FOOTER --> <footer class="footer"> <div class="footer-top"> <div class="container"> <div class="footer-brand"> <a href="#" class="logo">Gamics</a> <p class="footer-text"> Gamics marketplace the relase etras thats sheets continig passag. </p> <ul class="contact-list"> <li class="contact-item"> <div class="contact-icon"> <ion-icon name="location"></ion-icon> </div> <address class="item-text"> Address : PO Box W75 Street lan West new queens </address> </li> <li class="contact-item"> <div class="contact-icon"> <ion-icon name="headset"></ion-icon> </div> <a href="tel:+241245654235" class="item-text">Phone : +24 1245 654 235</a> </li> <li class="contact-item"> <div class="contact-icon"> <ion-icon name="mail-open"></ion-icon> </div> <a href="mailto:info@exemple.com" class="item-text">Email : info@exemple.com</a> </li> </ul> </div> <ul class="footer-list"> <li> <p class="footer-list-title">Products</p> </li> <li> <a href="#" class="footer-link">Graphics (26)</a> </li> <li> <a href="#" class="footer-link">Backgrounds (11)</a> </li> <li> <a href="#" class="footer-link">Fonts (9)</a> </li> <li> <a href="#" class="footer-link">Music (3)</a> </li> <li> <a href="#" class="footer-link">Photography (3)</a> </li> </ul> <ul class="footer-list"> <li> <p class="footer-list-title">Need Help?</p> </li> <li> <a href="#" class="footer-link">Terms & Conditions</a> </li> <li> <a href="#" class="footer-link">Privacy Policy</a> </li> <li> <a href="#" class="footer-link">Refund Policy</a> </li> <li> <a href="#" class="footer-link">Affiliate</a> </li> <li> <a href="#" class="footer-link">Use Cases</a> </li> </ul> <div class="footer-wrapper"> <div class="social-wrapper"> <p class="footer-list-title">Follow Us</p> <ul class="social-list"> <li> <a href="#" class="social-link" style="background-color: #3b5998"> <ion-icon name="logo-facebook"></ion-icon> </a> </li> <li> <a href="#" class="social-link" style="background-color: #55acee"> <ion-icon name="logo-twitter"></ion-icon> </a> </li> <li> <a href="#" class="social-link" style="background-color: #d71e18"> <ion-icon name="logo-pinterest"></ion-icon> </a> </li> <li> <a href="#" class="social-link" style="background-color: #1565c0"> <ion-icon name="logo-linkedin"></ion-icon> </a> </li> </ul> </div> <div class="footer-newsletter"> <p class="footer-list-title">Newsletter Sign Up</p> <form action="" class="footer-newsletter"> <input type="email" name="email_address" aria-label="email" placeholder="Enter your email" required class="email-field"> <button type="submit" class="footer-btn" aria-label="submit"> <ion-icon name="rocket"></ion-icon> </button> </form> </div> </div> </div> </div> <div class="footer-bottom"> <div class="container"> <p class="copyright"> &copy; 2022 Gamics. All Right Reserved by <a href="#" class="copyright-link">codewithsadee</a> </p> <img src="./assets/images/footer-bottom-img.png" width="340" height="21" loading="lazy" alt="" class="footer-bottom-img"> </div> </div> </footer> <!-- - #BACK TO TOP --> <a href="#top" class="back-top-btn" aria-label="back to top" data-back-top-btn> <ion-icon name="caret-up"></ion-icon> </a> <!-- - custom js link --> <script src="./assets/js/script.js" defer></script> <!-- - ionicon link --> <script type="module" src="https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.esm.js"></script> <script nomodule src="https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.js"></script> </body> </html>