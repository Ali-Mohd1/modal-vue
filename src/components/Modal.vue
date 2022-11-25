<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <p class="close" @click="closeModal">X</p>
      <slot></slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>
<style>
.modal {
  position: relative;
  width: 100%;
  max-width: 500px;
  padding: 20px 20px 40px;
  margin: 100px auto;
  background: #fff;
  border-radius: 10px;
}
.backdrop {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  padding: 0 15px;
}
.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
  color: #333;
}
.modal .actions a {
  color: rgba(38, 71, 241);
  padding: 8px 15px;
  border: 1px solid rgba(38, 71, 241);
  border-radius: 10px;
  text-decoration: none;
  margin: 10px;
}
.modal h1 {
  color: rgba(38, 71, 241);
  border: none;
  padding: none;
  margin-top: 20px;
}
p.close {
  position: absolute;
  right: 20px;
  top: 20px;
  width: 25px;
  height: 25px;
  background: #333;
  color: #ffff;
  display: grid;
  align-items: center;
  border-radius: 50px;
  font-weight: 700;
  font-size: 12px;
  cursor: pointer;
}
p.close:hover {
  background: #222;
}
form input {
  display: block;
  width: 100%;
  max-width: 350px;
  margin: 10px auto;
  height: 40px;
  padding: 0 10px;
  border: 1px solid #eee;
  border-radius: 10px;
}
form input:focus {
  outline-color: #ccc;
}
</style>
