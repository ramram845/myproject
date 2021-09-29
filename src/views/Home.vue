<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <v-sheet rounded elevation="3">
      <div class="text-h6 pa-4">このサイトは転職用のポートフォリオとして作成されました。</div>
      <div style="white-space:pre-line; word-wrap:break-word;">{{msg}}</div>
      <v-textarea
        label="input"
        v-model="msg"
        auto-grow class="ma-4"
        outlined
      >
        {{msg}}
      </v-textarea>
    </v-sheet>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data:() => ({
      msg:`このサイトはVue.jsとVuetifyを使用し作成されました。
下の入力フォームはVue.jsのリアクティブ性を確認するためのものです。
入力にあわせて文章が変化します。`
    })
}
</script>
