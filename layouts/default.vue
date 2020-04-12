<template>
  <div>
    <nuxt />
  </div>
</template>

<style lang="scss">
@import 'normalize.css';
@import url('https://fonts.googleapis.com/css2?family=M+PLUS+Rounded+1c:wght@400;800&display=swap');

*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  box-sizing: border-box;
  font-size: 16px;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}

body {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: 'M PLUS Rounded 1c', sans-serif;
  line-height: 1.8;
}

button {
  width: 100%;
  height: 100%;
  padding: 0;
  border: 0;
  background: transparent;
  cursor: pointer;
  appearance: none;

  &:active,
  &:focus {
    box-shadow: 0 0 0 3px rgba(83, 83, 83, 0.25);
  }
}
</style>
