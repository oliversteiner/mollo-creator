<template>
  <q-layout>
    <q-page-container>
      <q-page class='flex flex-center'>
        <q-btn
          color='white'
          class='absolute-top-right'
          flat
          round
          @click='$q.dark.toggle()'
          :icon="$q.dark.isActive ? 'nights_stay' : 'wb_sunny'"
        />
        <q-card
          class='login-form'
          v-bind:style="
            $q.platform.is.mobile ? { width: '80%' } : { width: '30%' }
          "
        >
          <q-card-section>
            <q-avatar
              size='74px'
              class='absolute'
              style='top: 0;right: 25px;transform: translateY(-50%);'
            >
              <img src='../assets/avatars/avatar.png' />
            </q-avatar>
            <div class='row no-wrap items-center'>
              <div class='col text-h6 ellipsis'>
                Log in to Dashboard
              </div>
            </div>
          </q-card-section>
          <q-card-section>
            <q-form class='q-gutter-md'>
              <q-input filled v-model='username' label='Username' autocomplete='username' lazy-rules />

              <q-input
                type='password'
                filled
                v-model='password'
                label='Password'
                autocomplete='password'
                lazy-rules
              />

              <div>
                <q-btn
                  label='Login'
                  type='button'
                  color='primary'
                  @click='loginNotify'
                />
              </div>
            </q-form>
          </q-card-section>
        </q-card>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script lang='ts'>
import { defineComponent } from '@vue/composition-api';
import { api } from 'boot/axios';
import { Quasar } from 'quasar';

export default defineComponent({
  name: 'login',
  data: [],
  beforeCreate() {
    this.$q.dark.set(true);
    console.log(this.$q.dark.isActive); // true, false
  },

  props: {
    username: {
      type: String,
      default: 'admin'
    },
    password: {
      type: String,
      default: 'Admin@CRM'
    }
  },
  methods: {
    loginNotify() {
      this.loadData();
      this.$q.notify({
        message: 'Login Successful'
      });
    },

    loadData() {
      api.post('/user/login?_format=json', {
        name: 'admin',
        pass: 'finder-manse-UNSTRUNG-eldest'
      })
        .then((response) => {
          this.data = response.data;
          console.log('Log in try', response.data);

        })
        .catch(() => {
          this.$q.notify({
            color: 'negative',
            position: 'top',
            message: 'Loading failed',
            icon: 'report_problem'
          });
        });
    }

  },
  setup(props) {
    const $q = Quasar;

    // showing an example on a method, but
    // can be any part of Vue script
    function show() {
      // prints out Quasar version
      console.log(this.$q.version);
      console.log('Login:', props);
    }


    return {
      show
    };
  }
});
</script>

<style>


.login-form {
  position: absolute;
}
</style>
