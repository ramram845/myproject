<template>
  <v-expansion-panels multiple class="ma-2">

    <v-expansion-panel>

      <v-expansion-panel-header color="blue darken-1" class="white--text">
        うるう年の判別
      </v-expansion-panel-header>

      <v-expansion-panel-content class="text-left">
        <div class="my-4">
          入力された年がうるう年かどうか判別します。<br>
          西暦1年から1万年まで対応しています。<br>
          <v-text-field label="Year" v-model="inputYear"></v-text-field>
        </div>
          <span v-if="inputYear">
            <v-alert :type="isSuccess" >{{isInputYear(inputYear)}}{{msg}}</v-alert>
          </span>
      </v-expansion-panel-content>

    </v-expansion-panel>

  </v-expansion-panels>
</template>

<script>
export default {
  components: {
      
  },
  data () {
    return {
      inputYear:'',
      isSuccess:'success',
      msg:''
    }
  },
    
  methods:{
    isInputYear(){
      if(!Number.isInteger(Number(this.inputYear))){
        this.isSuccess = "warning"
        this.msg = '半角数字の整数で入力してください。'
        return ''
      } 

      if(this.inputYear < 1 || 10000 < this.inputYear)
      {
      this.isSuccess = "warning"
      this.msg = '入力年数が範囲外です。'
       return ''
      }
      this.inputYear = parseInt(this.inputYear)

      if(this.inputYear % 400 == 0){
        this.isSuccess = 'success'
        this.msg = this.inputYear + '年はうるう年です。'
        return ''
      }else if(this.inputYear % 100 == 0){
        this.isSuccess = 'info'
        this.msg = this.inputYear + '年はうるう年ではありません。'
        return ''
      }else if(this.inputYear % 4 == 0){
        this.isSuccess = 'success'
        this.msg = this.inputYear + '年はうるう年です。'
        return ''
      }else{
        this.isSuccess = 'info'
        this.msg = this.inputYear + '年はうるう年ではありません。'
        return ''
      }
    


    }
  }
}
</script>
