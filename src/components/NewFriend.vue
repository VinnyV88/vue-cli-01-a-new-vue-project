<template>
  <section id="new-friend">
    <div>
      <h2>Enter a New Friend</h2>
    </div>
    <form>
      <div>
        <label for="id">ID</label>
        <input type="text" v-model="id" />
      </div>
      <div>
        <label for="name">Name</label>
        <input type="text" v-model="name" />
      </div>
      <div>
        <label for="phone">Phone Number</label>
        <input type="tel" v-model="phone" />
      </div>
      <div>
        <label for="email">Email</label>
        <input type="email" v-model="email" />
      </div>
      <div>
        <label for="favorite">Is Favorite</label>
        <input type="text" v-model="favorite" />
      </div>
      <div>
        <button @click.prevent="addFriend">Add New Friend</button>
      </div>
    </form>
  </section>
</template>

<script>
export default {
  emits: ["add-new-friend"],
  data() {
    return {
      id: "",
      name: "",
      phone: "",
      email: "",
      favorite: "",
    };
  },
  methods: {
    addFriend() {
      let isFav;
      if (this.favorite === "1") {
        isFav = true;
      } else {
        isFav = false;
      }
      this.$emit(
        "add-new-friend",
        this.id,
        this.name,
        this.phone,
        this.email,
        isFav
      );
    },
  },
};
</script>
