<template>

  <v-container grid-list-xl>

    <v-layout row justify-center>
      <v-flex xs3>
        <v-btn
          block 
          :button="button1"
          :disabled="loading1"
          color="success"
          @click="loader = 'loading1'"
        >
          Операции с наличными
          <template v-slot:loader>
            <span>Loading...</span>
          </template>
        </v-btn>
      </v-flex>
      <v-flex xs3>
        <v-btn
          block
          :loading="loading2"
          :disabled="loading2"
          color="success"
          @click="loader = 'loading2'"
        >
          Оплата телефона
          <template v-slot:loader>
            <span>Loading...</span>
          </template>
        </v-btn>
      </v-flex>
    </v-layout>

    <v-layout row justify-center>
      <v-flex xs3>
        <v-btn
          block 
          :loading="loading3"
          :disabled="loading3"
          color="success"
          @click="loader = 'loading3'"
        >
          Информация и сервис
          <template v-slot:loader>
            <span>Loading...</span>
          </template>
        </v-btn>
      </v-flex>
      <v-flex xs3>
        <v-btn
          block 
          :loading="loading4"
          :disabled="loading4"
          color="success"
          @click="loader = 'loading4'"
        >
          Оплата мобильной связи
          <template v-slot:loader>
            <span>Loading...</span>
          </template>
        </v-btn>
      </v-flex>
    </v-layout>
    
    <v-layout row justify-center>
      <v-flex xs3>
        <v-btn
          block 
          :loading="loading5"
          :disabled="loading5"
          color="success"
          @click="loader = 'loading5'"
        >
          Личный кабинет
          <template v-slot:loader>
            <span>Loading...</span>
          </template>
        </v-btn>
      </v-flex>
      <v-flex xs3>
        <v-btn
          block 
          :loading="loading6"
          :disabled="loading6"
          color="success"
          @click="loader = 'loading6'"
        >
          Custom Loader
          <template v-slot:loader>
            <span>Loading...</span>
          </template>
        </v-btn>
      </v-flex>
    </v-layout>


  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        loader: null,
        loading1: false,
        loading2: false,
        loading3: false,
        loading4: false,
        loading5: false,
        loading6: false
      }
    },
    watch: {
      loader () {
        const l = this.loader
        this[l] = !this[l]

        setTimeout(() => (this[l] = false), 3000)

        this.loader = null
      }
    }
  }
</script>


<style>
  .custom-loader {
    animation: loader 1s infinite;
    display: flex;
  }
</style>
