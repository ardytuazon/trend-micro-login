<template>
  <div class="input-box">
    <label :for="name" class="custom-field">
      <input
        :type="type"
        :id="name"
        class="form-input"
        autocomplete="off"
        required
      />
      <span class="placeholder"><slot /></span>
    </label>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    type: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.input-box {
  position: relative;
  font-size: 14px;
  margin: 10px 0;
}
.custom-field .placeholder {
  position: absolute;
  left: 10px;
  top: calc(50%);
  transform: translateY(-50%);
  transition: all 0.3s ease;
}
.custom-field input {
  width: calc(100% - 10px);
  border-radius: 5px;
  border: 0;
  background: #f1f5ff;
  color: #000;
  font-size: 14px;
  outline: none;
  padding: 17px 1px 5px 10px;
}
.custom-field input:focus + .placeholder,
.custom-field input:valid + .placeholder {
  top: 10px;
  color: #757575;
  font-size: 10px;
}
.input-box .password-icon {
  position: absolute;
  right: 10px;
  top: 10px;
}
</style>