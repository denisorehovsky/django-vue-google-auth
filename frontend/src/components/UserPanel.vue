<template>
  <div class="panel">
    <div class="panel-header text-center">
      <figure class="avatar avatar-lg">
        <img :src="user.photo" alt="Avatar">
      </figure>
      <div class="panel-title h5 mt-10">{{ user.first_name }} {{ user.last_name }}</div>
      <div class="panel-subtitle">{{ user.username }}</div>
    </div>
    <nav class="panel-nav">
      <ul class="tab tab-block">
        <li class="tab-item active">
          <a>Profile</a>
        </li>
      </ul>
    </nav>
    <div class="panel-body">
      <div class="tile tile-centered">
        <div class="tile-content">
          <div class="tile-title">E-mail</div>
          <div class="tile-subtitle">{{ user.email }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserPanel',
  props: ['user']
}
</script>
