<template>
  <div class="container">
    <div class="img-container">
      <div class="profile-img" />
    </div>
    <div class="profile-info">
      <h1 data-splitting class="title">Kishore Kumar</h1>
      <h5 class="sub-title" data-splitting>Front-End Developer</h5>
      <section class="media-platforms">
        <a href="https://twitter.com/Kishore01Kumar" rel="noopener" target="_blank">
          <img src="../static/svgs/twitter.svg"/>
        </a>
        <a href="https://github.com/kishoreyuvan" rel="noopener" target="_blank">
          <img src="../static/svgs/github.svg"/>
        </a>
        <a href="https://www.linkedin.com/in/kishore-kumar-b63458171/" rel="noopener" target="_blank">
          <img src="../static/svgs/linkedin.svg"/>
        </a>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  head: {
   title: 'Kishore Kumar Bio',
   meta: [
     { charset: 'utf-8' },
     { name: 'viewport', content: 'width=device-width, initial-scale=1' },
     {
       hid: 'description',
       name: 'description',
       content: 'Kishore Kumar Portfolio'
     }
   ],
   script: [
      {
        src: 'https://unpkg.com/splitting/dist/splitting.min.js'
      }
    ],
   link: [
     {
       rel: 'icon',
       type: 'image/x-icon',
       href: '/favicon.ico'
     },
     {
       rel: 'stylesheet',
       href: 'https://unpkg.com/splitting/dist/splitting.css'
     }
   ]
 },

 mounted() {
   Splitting();
 }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  color: #fff;
  font-family: 'Lexend Deca', sans-serif;
  background: #0F2027;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #2C5364, #203A43, #0F2027);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #2C5364, #203A43, #0F2027); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
.img-container {
  margin-right: 50px;
}
.profile-img {
  width: 300px;
  height: 300px;
  border-radius: 20px;
  background-image: url('../assets/kishore.jpeg');
  background-size: cover;
  box-shadow: 0 0 20px 20px #2C5364 inset;
  animation: swift 0.5s ease-in;
}
.profile-info .title {
  text-transform: uppercase;
  font-size: 50px;
  margin-bottom: 10px;
}
.profile-info .sub-title {
  font-size: 25px;
  margin-bottom: 20px;
}
.profile-info .title .char {
  transform-origin: 50% 100%;
  animation: rise 3s cubic-bezier(0.25, 0.46, 0.45, 0.94) calc(var(--distance-percent) * 0.125s);
}

.profile-info .title .char::after {
  animation: ghost 3s ease-in calc(var(--distance-percent) * 0.125s);
  content: attr(data-char);
  opacity: 0;
  transform-origin: 100% 50%;
  visibility: visible;
}
.profile-info .sub-title .char {
  animation: float 3s ease-in-out calc(var(--char-index) * -0.5s) infinite;
}
.media-platforms img {
  width: 25px;
  margin-right: 5px;
  filter: invert(1);
}

@keyframes swift {
  0% {
    opacity: 0;
    transform: scale(0);
  },
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes rise {
  40% {
    transform:
      translateY(-40%)
      rotate(calc(var(--distance-sine) * 10deg)
    );
  }
  50% { transform: translateY( 6%); }
  55% { transform: translateY(-4%); }
  60% { transform: translateY( 2%); }
  65% { transform: translateY(-1%); }
  70% { transform: translateY( 0%); }
}

@keyframes ghost {
  40% {
    opacity: 0.25;
    transform:
      translateY(-50%)
      rotate(calc(var(--distance-sine) * -10deg)
    );
  }
  60%, 100% {
    opacity: 0;
    transform: translateY(-200%);
  }
}

@keyframes float {
   0%, 100% {
     transform: translate(2%, -10%) rotate(-1deg);
   }
   50% {
     transform: translate(-2%, 5%) rotate(3deg);
   }
 }
</style>
