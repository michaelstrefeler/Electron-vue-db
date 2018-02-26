<template>
    <main>
      <div class="left-side">
        <span class="title">
          {{ message }}
        </span>
        <p>Data from json database :</p>
        <p class="dataTitle">Users</p>
        <div v-for="user in users" :key="user.id">
          {{ user.username }} {{ user.password }}
        </div>
        <br>
        <p class="dataTitle">Shopping lists</p>
        <div v-for="list in lists" :key="list.id">
          {{ list.name }}:
          <div v-for="item in list.contents" :key="item.id">
            {{ item }}
          </div>
          <br>
        </div>
      </div>

      <div class="right-side">
        <div class="doc">
          <div class="title">About</div>
          <p>
            This is a second component that I made called "more.vue". I'm gonna try to make the strefeld-mgmt website in electron-vue.
            I think that it's gonna be fun and that I'm gonna learn a lot. I was wrong
          </p>
          <br>
          <button @click="open('https://github.com/michaelstrefeler')">Go to my Github profile</button><br><br>
        </div>
        <p class="dataTitle">Reminders</p>
        <div v-for="event in reminders" :key="event.id">
          {{ event.title }} {{ event.date }} {{ event.time }} {{ event.concernedParty }}
        </div>
        <br>
      </div>
    </main>
</template>

<script>
// import JSON database
import db from './dbJSONtest'
export default {
  name: 'more',
  data () {
    return {
      message: 'Greetings',
      users: db.table.user,
      lists: db.table.shoppingList,
      reminders: db.table.reminder
    }
  },
  methods: {
    open (link) {
      this.$electron.shell.openExternal(link)
    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro');

  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body { font-family: 'Source Sans Pro', sans-serif; }

  #wrapper {
    background:
      radial-gradient(
        ellipse at top left,
        rgba(255, 255, 255, 1) 40%,
        rgba(229, 229, 229, .9) 100%
      );
    height: 100vh;
    padding: 20px 80px 60px;
    width: 100vw;
  }

  #logo {
    height: auto;
    margin-bottom: 20px;
    width: 420px;
  }

  main {
    display: flex;
    justify-content: space-between;
  }

  main > div { flex-basis: 50%; }

  .left-side {
    display: flex;
    flex-direction: column;
  }

  .welcome {
    color: #555;
    font-size: 23px;
    margin-bottom: 10px;
  }

  .title {
    color: #2c3e50;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 6px;
  }

  .title.alt {
    font-size: 18px;
    margin-bottom: 10px;
  }

  .doc p {
    color: black;
    margin-bottom: 10px;
  }

  .doc button {
    font-size: .8em;
    cursor: pointer;
    outline: none;
    padding: 0.75em 2em;
    border-radius: 2em;
    display: inline-block;
    color: #fff;
    background-color: #4fc08d;
    transition: all 0.15s ease;
    box-sizing: border-box;
    border: 1px solid #4fc08d;
  }

  .doc button.alt {
    color: #42b983;
    background-color: transparent;
  }

  .dataTitle{
    text-decoration: underline;
  }
</style>
