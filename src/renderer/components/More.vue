<template>
  <Row>
    <main>
    <Col span="12">
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
      <br>

      <div v-for="list in lists" :key="list.id" style="float:left">
        {{ list.name }} &nbsp&nbsp&nbsp&nbsp
        <div v-for="item in list.contents" :key="item.id">
          {{ item }}
        </div>
        <br>
      </div>
      </Col>

      <Col span="12">
        <div class="doc">
          <div class="title">About</div>
          <p>
            This is a second component that I made called "more.vue". I'm gonna try to make the strefeld-mgmt website in electron-vue.
            I think that it's gonna be fun and that I'm gonna learn a lot.
          </p>
          <br>
          <Button type="primary" @click="open('https://github.com/michaelstrefeler')">Go to my Github profile</Button><br><br>
        </div>
        <p class="dataTitle">Reminders</p>
        <div v-for="event in reminders" :key="event.id">
          {{ event.title }} {{ event.date }} {{ event.time }} {{ event.concernedParty }}
        </div>
        <br>
      </Col>
    </main>
  </Row>
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

<style scoped>
  /* CSS */
</style>
