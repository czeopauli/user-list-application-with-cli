<template>
  <div class="user-listdetails">
    <h2 class="user-listdetails-hl">Details</h2>
    <template v-if="user">
      <dl>
        <dt>name:</dt>
        <dd>{{ user.name }}</dd>

        <dt>email:</dt>
        <dd>{{ user.email }}</dd>

        <dt>phone:</dt>
        <dd>{{ user.phone }}</dd>

        <dt>company:</dt>
        <dd>{{ user.company.name }}</dd>
      </dl>
    </template>
    <template v-else>
      <p class="user-list__details-hint">
        Es wurde kein Nutzer gefunden / ausgewählt
      </p>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    user: Object,
  },
  created() {
    console.log("Received User in UserListDetail:", this.user);
  },
};
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
}
.user-list__details {
  width: 60%;
  padding: 1rem;
  color: #192a56;
  font-family: Arial, Helvetica, sans-serif;
}
.user-listdetails-hl {
  color: #00a8ff;
  font-size: 2rem;
  margin-top: 1.5rem;
}
.user-listdetails dl dt {
  font-weight: bold;
  margin-top: 10px;
}

.user-listdetails dl dd {
  margin-left: 0;
  margin-bottom: 10px;
}
.user-list__details-hint {
  margin-top: 1rem;
  border: 3px solid #e84118;
  font-size: 1.2rem;
  border-radius: 5px;
  color: #e84118;
  padding: 0.5rem;
  margin-right: 1rem;
}
</style>
