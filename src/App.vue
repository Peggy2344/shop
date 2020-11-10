<template lang="pug">
#app
  b-container
    b-row
      b-col.text-center(cols="12")
        #nav
          router-link(to='/') Home
          |  |
          router-link(to='/about') About
      b-col(cols="12")
        router-view
</template>
