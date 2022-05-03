<template>
  <div>
    <Header></Header>
    <NuxtPage />
  </div>
</template>

<style lang="css">
@import url('https://fonts.googleapis.com/css2?family=Days+One&family=Lato:wght@300&family=Roboto&display=swap');

html, body{
  color: #FFF;
  width: 100%;
  margin: 0;
  padding: 0;
  border: 0;
  font-family: 'Roboto', sans-serif;
}

* {
  box-sizing: border-box;
}

::-webkit-scrollbar {
  width: 10px;
  height: 10px;
}

::-webkit-scrollbar-thumb {
  background: rgba(90, 90, 90);
}

::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0.2);
}
</style>