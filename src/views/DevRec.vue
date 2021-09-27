<template>
  <div class="devRec" :style="{ background: $vuetify.theme.themes.light.background2 }">
  <v-expansion-panels multiple class="ma-2">

    <v-expansion-panel>
      <v-expansion-panel-header color="blue darken-1" class="white--text">
        開発環境の構築〜サイト公開まで
      </v-expansion-panel-header>

      <v-expansion-panel-content class="text-left mt-4">
        環境構築〜サイト公開までの流れは<br>
        １：AWSのみでサイトを公開<br>
        ２：仮想環境を構築<br>
        ３：Vueのみでサイトを作成<br>
        ４：AWSとVueでサイトを公開<br>
        の順になります。<br>
        まずAWSの公式サイトでVue抜きの知識を得ました。<br>
        <a href = "https://aws.amazon.com/jp/getting-started/hands-on/build-web-app-s3-lambda-api-gateway-dynamodb/?e=gs2020&p=fullstack">
        https://aws.amazon.com/jp/getting-started/hands-on/build-web-app-s3-lambda-api-gateway-dynamodb/?e=gs2020&p=fullstack</a><br>
        <br>
        次にVue単体でサイトを作成したかったので仮想PCを作成することにしました。<br>
        仮想PCソフトはVMWare、ディストリビューションはUbuntuにしました。<br>
        VMWareにした理由は以前に触ったことがあったからです。<br>
        Ubuntuにした理由は何かのサイトでUbuntuを使用していたのを見た事と、<br>
        メジャーなディストリビューションである事です。<br>
        環境とOS自体は何でも大丈夫です。<br>
        <br>
        次にNode.js、npm、VueCLI、Vuetify、gitをインストールしました。<br>
        Ubuntuではinstallコマンドを実行する際にsudoコマンドを入力する必要があります。<br>
        vue.config.jsを作成し相対パスを設定しなければ上手くビルドできません。<br>
        以上のパッケージでローカルでサイトを作成することができます。<br>
        あとはビルドしたフォルダをAWSに上げてサイトを公開することができます。<br>
      </v-expansion-panel-content>
    </v-expansion-panel>

    <v-expansion-panel>
      <v-expansion-panel-header color="blue darken-1" class="white--text">
        ヘッダー、タブ、最初のソフトの作成
      </v-expansion-panel-header>
      
      <v-expansion-panel-content class="text-left mt-4">
        ヘッダーはVuetifyの公式サイトを参考に作成しました。<br>
        <a href ="https://vuetifyjs.com/ja/">
        https://vuetifyjs.com/ja/</a><br>
        初期はカラーのPropsが反映されませんでしたが、v-appタグの中にv-app-barタグがないことが原因でした。<br>
        タグの作成はVueRouterを使用しました。<br>
        <br>
        最初のソフトとしては関数の呼び出しとVuetifyの入力フォームを利用したもので、かつ簡単に作れるものと考え、<br>
        入力された年がうるう年かどうか判別するソフトを作ることにしました。<br>
        しかし、ここで躓いた点がありました。<br>
        入力値が半角数字の整数が正常な入力で、それ以外がエラー処理をするコードを書いたつもりでした。<br>
        ですが、半角数字の整数でもエラー処理が呼び出されてしまいました。<br>
        調べた結果としては、整数であればtrueを返すNumber.isInteger()関数が、<br>
        文字列を渡すと半角数字でもfalseを返す仕様のためでした。<br>
        実数として値を渡せば正しく動きました。<br>

        また、このソフトで珍しい動きも見られました。<br>
        10.00などの数値が渡された時に整数として扱われるので、<br>
        整数以外の入力を弾いた後に入力値=parseInt(入力値)で小数点以下を切り捨てる処理を入れました。<br>
        以上の処理を書いたところ、双方向バインディングなのでフォームの入力値も小数点以下が切り捨てられました。<br>
        変数を用意して入力値を代入すれば以上の動きは回避できますが、あまり見ない動きなので残しておく事にしました。<br>
        10.00などの数値を入力して整数部分を変更すれば見ることができます。
      </v-expansion-panel-content>
    </v-expansion-panel>

    <v-expansion-panel>
      <v-expansion-panel-header color="blue darken-1" class="white--text">
      </v-expansion-panel-header>
      
      <v-expansion-panel-content class="text-left mt-4">
      </v-expansion-panel-content>
    </v-expansion-panel>

  </v-expansion-panels>
  </div>
</template>

<script>
    export default {
    components: {
    },
}
</script>