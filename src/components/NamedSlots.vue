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
  color: red;
}

main {
  color: blue;
}

footer {
  color: yellow;
}
</style>

