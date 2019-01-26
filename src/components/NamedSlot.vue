<template>
  <div>
    <header>
      <slot name="header"></slot>
    </header>
    <main>
      <slot></slot>
    </main>
    <footer>
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<style scoped>
header {
  background-color: crimson;
  color: white;
  font-size: 44px;
}

main {
  color: blue;
  font-size: 26px;
}

footer {
  color: black;
  background-color: yellow;
  padding: 20px;
}
</style>

