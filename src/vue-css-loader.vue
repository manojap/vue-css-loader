<template>
  <div>
    <div class="ct" v-if="animation === 'Dots'">
      <div class="dots" />
    </div>
    <div class="ct" v-else-if="animation === 'Circle'">
      <div class="circle"></div>
    </div>
    <div class="ct" v-else-if="animation === 'BouncingBars'">
      <div class="bouncing_bar">
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
      </div>
    </div>
    <div class="ct" v-else-if="animation === 'SpinnerDots'">
      <div class="spinner_dots" />
    </div>
    <div class="ct" v-else-if="animation === 'Focus'">
      <div class="focus" />
    </div>
    <div class="ct" v-else-if="animation === 'TwinCircles'">
      <div class="twin_circles" />
    </div>
    <div class="ct" v-else-if="animation === 'Wave'">
      <div class="wave" />
    </div>
    <div class="ct" v-else>
      <div class="wave" />
    </div>
  </div>
</template>

<script>
export default /*#__PURE__*/ {
  name: "VueCssLoader", // vue component name
  props: {
    animation: String,
    defaultValue: "Circle",
  },
};
</script>

<style scoped>
.ct {
  padding-top: 20px;
  padding-bottom: 20px;
  padding-left: 20px;
  padding-right: 10px;
}
.box {
  width: calc(25% - 12px);
  height: 10%;
  background-color: #fff;
  border-radius: 4px;
  margin: 16px 6px;
  box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
}

.dots {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  position: relative;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background-color: var(--icon-color);
  opacity: 1;
  -webkit-animation: dot-middle 1s infinite linear;
  animation: dot-middle 1s infinite linear;
}
.dots:before,
.dots:after {
  content: "";
  position: absolute;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background-color: var(--icon-color);
}
.dots:before {
  left: -28px;
  opacity: 0.25;
  -webkit-animation: dot-left 1s infinite linear;
  animation: dot-left 1s infinite linear;
}
.dots:after {
  left: 28px;
  opacity: 1;
  -webkit-animation: dot-right 1s infinite linear;
  animation: dot-right 1s infinite linear;
}

@-webkit-keyframes dot-middle {
  0% {
    opacity: 1;
  }
  33% {
    opacity: 0.25;
  }
  66% {
    opacity: 0.25;
  }
  100% {
    opacity: 1;
  }
}

@keyframes dot-middle {
  0% {
    opacity: 1;
  }
  33% {
    opacity: 0.25;
  }
  66% {
    opacity: 0.25;
  }
  100% {
    opacity: 1;
  }
}
@-webkit-keyframes dot-left {
  0% {
    opacity: 0.25;
  }
  33% {
    opacity: 1;
  }
  66% {
    opacity: 0.25;
  }
}
@keyframes dot-left {
  0% {
    opacity: 0.25;
  }
  33% {
    opacity: 1;
  }
  66% {
    opacity: 0.25;
  }
}
@-webkit-keyframes dot-right {
  33% {
    opacity: 0.25;
  }
  66% {
    opacity: 1;
  }
  100% {
    opacity: 0.25;
  }
}
@keyframes dot-right {
  33% {
    opacity: 0.25;
  }
  66% {
    opacity: 1;
  }
  100% {
    opacity: 0.25;
  }
}
.twin_circles {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  position: relative;
}
.twin_circles:before,
.twin_circles:after {
  content: "";
  position: absolute;
  border-radius: 50%;
  width: 20px;
  height: 20px;
  background: var(--icon-color);
  /* top: calc(50% - 10px);
  left: calc(50% - 10px); */
  -webkit-animation: 2s ease-in-out infinite;
  animation: 2s ease-in-out infinite;
  -webkit-animation-direction: alternate;
  animation-direction: alternate;
}
.twin_circles:before {
  opacity: 0.7;
  -webkit-animation-name: moveLeft;
  animation-name: moveLeft;
}
.twin_circles:after {
  opacity: 0.5;
  -webkit-animation-name: moveRight;
  animation-name: moveRight;
}

@-webkit-keyframes moveLeft {
  25% {
    transform: translatex(-50%);
  }
  50%,
  60% {
    transform: translatex(0);
  }
  100% {
    transform: translatex(50%);
  }
}

@keyframes moveLeft {
  25% {
    transform: translatex(-50%);
  }
  50%,
  60% {
    transform: translatex(0);
  }
  100% {
    transform: translatex(50%);
  }
}
@-webkit-keyframes moveRight {
  25% {
    transform: translatex(50%);
  }
  50%,
  60% {
    transform: translatex(0);
  }
  100% {
    transform: translatex(-50%);
  }
}
@keyframes moveRight {
  25% {
    transform: translatex(50%);
  }
  50%,
  60% {
    transform: translatex(0);
  }
  100% {
    transform: translatex(-50%);
  }
}
.wave {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  position: relative;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  opacity: 1;
}
.wave:before,
.wave:after {
  content: "";
  position: absolute;
  border-radius: 50%;
  border: 1px var(--icon-color) solid;
  width: 100%;
  height: 100%;
  left: 0px;
}
.wave:before {
  -webkit-animation: wave-outer 0.6s infinite linear;
  animation: wave-outer 0.6s infinite linear;
  transform: scale(1);
  opacity: 1;
}
.wave:after {
  -webkit-animation: wave-inner 0.6s infinite linear;
  animation: wave-inner 0.6s infinite linear;
  transform: scale(0);
  opacity: 0;
}

@-webkit-keyframes wave-outer {
  from {
    opacity: 1;
    transform: scale(1);
  }
  to {
    opacity: 0;
    transform: scale(1.5);
  }
}

@keyframes wave-outer {
  from {
    opacity: 1;
    transform: scale(1);
  }
  to {
    opacity: 0;
    transform: scale(1.5);
  }
}
@-webkit-keyframes wave-inner {
  from {
    opacity: 0;
    transform: scale(0.5);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
@keyframes wave-inner {
  from {
    opacity: 0;
    transform: scale(0.5);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
.circle {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  width: 50px;
  height: 50px;
  border: 6px var(--icon-color-lighten) solid;
  border-top: 6px var(--icon-color) solid;
  border-radius: 50%;
  -webkit-animation: spin-circle 0.8s infinite linear;
  animation: spin-circle 0.8s infinite linear;
}

@-webkit-keyframes spin-circle {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@keyframes spin-circle {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
.focus {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  position: relative;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: var(--icon-color);
}
.focus:before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 6px solid #fff;
  top: -6px;
  left: -6px;
  -webkit-animation: focus 1s infinite ease-in-out;
  animation: focus 1s infinite ease-in-out;
}

@-webkit-keyframes focus {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}

@keyframes focus {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}
.bouncing_bar {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  display: flex;
  /* align-items: center; */
}

.line {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  height: 20px;
  width: 4px;
  background: var(--icon-color);
  margin-right: 4px;
  border-radius: 6px;
  -webkit-animation: line-bounce 1s infinite ease-in-out;
  animation: line-bounce 1s infinite ease-in-out;
}
.line:nth-child(1) {
  -webkit-animation-delay: 0s;
  animation-delay: 0s;
}
.line:nth-child(2) {
  -webkit-animation-delay: 0.2s;
  animation-delay: 0.2s;
}
.line:nth-child(3) {
  -webkit-animation-delay: 0.3s;
  animation-delay: 0.3s;
}
.line:nth-child(4) {
  -webkit-animation-delay: 0.4s;
  animation-delay: 0.4s;
}

@-webkit-keyframes line-bounce {
  0% {
    transform: scale(1);
  }
  20% {
    transform: scale(1, 2);
  }
  40% {
    transform: scale(1);
  }
}

@keyframes line-bounce {
  0% {
    transform: scale(1);
  }
  20% {
    transform: scale(1, 2);
  }
  40% {
    transform: scale(1);
  }
}
.spinner_dots {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  position: relative;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background-color: var(--icon-color);
  opacity: 1;
  transform-origin: 50% 50%;
  -webkit-animation: spin-dot 1s infinite linear;
  animation: spin-dot 1s infinite linear;
}
.spinner_dots:before,
.spinner_dots:after {
  content: "";
  position: absolute;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background-color: var(--icon-color);
}
.spinner_dots:before {
  left: -28px;
  opacity: 0.25;
}
.spinner_dots:after {
  left: 28px;
  opacity: 0.25;
}

@-webkit-keyframes spin-dot {
  0% {
    transform: rotate(0deg);
  }
  50% {
    transform: rotate(180deg);
  }
  100% {
    transform: rotate(180deg);
  }
}

@keyframes spin-dot {
  0% {
    transform: rotate(0deg);
  }
  50% {
    transform: rotate(180deg);
  }
  100% {
    transform: rotate(180deg);
  }
}
.fading_lines {
  --icon-color: rgb(2, 90, 108);
  --icon-color-lighten: rgba(2, 90, 108, 0.25);
  position: relative;
  background: var(--icon-color);
  width: 4px;
  height: 32px;
  border-radius: 6px;
  -webkit-animation: jump-load-1 1s ease infinite alternate;
  animation: jump-load-1 1s ease infinite alternate;
  -webkit-animation-delay: 0.25s;
  animation-delay: 0.25s;
}
.fading_lines:before,
.fading_lines:after {
  content: "";
  position: absolute;
  background: var(--icon-color);
  width: 4px;
  height: 32px;
  border-radius: 6px;
  top: 0;
  -webkit-animation: jump-load-2 1s ease infinite;
  animation: jump-load-2 1s ease infinite;
  -webkit-animation-direction: alternate;
  animation-direction: alternate;
}
.fading_lines:before {
  left: -8px;
}
.fading_lines:after {
  left: 8px;
  -webkit-animation-delay: 0.4s;
  animation-delay: 0.4s;
}

@-webkit-keyframes jump-load-1 {
  from {
    transform: translateY(20px);
  }
  to {
    transform: translateY(-16px);
  }
}

@keyframes jump-load-1 {
  from {
    transform: translateY(20px);
  }
  to {
    transform: translateY(-16px);
  }
}
@-webkit-keyframes jump-load-2 {
  from {
    transform: translateY(16px);
  }
  to {
    transform: translateY(-16x);
  }
}
@keyframes jump-load-2 {
  from {
    transform: translateY(16px);
  }
  to {
    transform: translateY(-16x);
  }
}
@media screen and (max-width: 520px) {
  .box {
    width: calc(50% - 20px);
  }
}
</style>
