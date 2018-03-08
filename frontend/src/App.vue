<template>
  <div id="app">
    <div class="container">
      <div class="columns" style="margin-top: 100px;">
        <div class="column col-2 centered">
          <g-signin-button
            v-if="isEmpty(user)"
            :params="googleSignInParams"
            @success="onGoogleSignInSuccess"
            @error="onGoogleSignInError"
          >
            <button class="btn btn-block btn-success">
              Google Signin
            </button>
          </g-signin-button>
          <user-panel v-else :user="user"></user-panel>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

import UserPanel from '@/components/UserPanel'

export default {
  name: 'App',
  components: {
    UserPanel
  },
  data () {
    return {
      user: {},
      googleSignInParams: {
        client_id: '600729137370-h25svjos6nbofm48mmtacd3hjq6ogu95.apps.googleusercontent.com'
      }
    }
  },
  methods: {
    onGoogleSignInSuccess (resp) {
      const token = resp.Zi.access_token
      axios.post('http://localhost:8000/auth/google/', {
        access_token: token
      })
        .then(resp => {
          this.user = resp.data.user
        })
        .catch(err => {
          console.log(err.response)
        })
    },
    onGoogleSignInError (error) {
      console.log('OH NOES', error)
    },
    isEmpty (obj) {
      return Object.keys(obj).length === 0
    }
  }
}
</script>
