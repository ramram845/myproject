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
        単一のPCで一名のみで開発しているためです。<br>
      </v-expansion-panel-content>
    </v-expansion-panel>

    <v-expansion-panel>
      <v-expansion-panel-header color="blue darken-1" class="white--text">
        ヘッダー、タブ、最初のソフトの作成
      </v-expansion-panel-header>
      
      <v-expansion-panel-content class="text-left mt-4">

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