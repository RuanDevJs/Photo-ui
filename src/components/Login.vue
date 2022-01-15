<template>
  <section class="form">
    <form class="form-container">
      <h1>Login</h1>
      <div class="form-wrap">
        <label for="email">E-mail</label>
        <input type="text" placeholder="Insira seu e-mail" />
      </div>
      <div class="form-wrap">
        <label for="email">Senha</label>
        <input type="password" placeholder="Insira sua senha" />
      </div>
      <button class="form-submit">Acessar</button>
    </form>
  </section>
</template>

<script>
export default {
  name: "Login",
};
</script>

<style scoped>
.form {
  padding: 50px;
  height: 100vh;
  background: linear-gradient(to right, #1a1a1a 30%);
  position: relative;
}

.form::before {
  content: "";
  display: block;
  height: 300px;
  width: 300px;
  background: #84e;
  border-bottom-right-radius: 100%;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}

.form::after {
  content: "";
  display: block;
  height: 300px;
  width: 300px;
  background: #82e;
  border-top-left-radius: 100%;
  position: absolute;
  bottom: 0;
  right: 0;
}

.form-container {
  display: flex;
  flex-flow: column wrap;
  align-items: center;
}

.form-container h1 {
  font-size: 32px;
  font-weight: 500;
  color: #333;
  padding: 5px 5px 0 5px;
}

.form-container p {
  color: #1a1a1a;
}

.form-wrap {
  display: flex;
  flex-direction: column;
  margin: 4px 0;
}

.form-wrap > label {
  font-size: 18px;
  font-weight: 400;
  color: #c2c2c2;
}

.form-wrap > input {
  outline: 0;
  border: 1px solid #f2f2f2;

  background: #fff;
  width: 360px;
  padding: 16px;
  margin: 8px 0;

  font-size: 18px;
  font-weight: 500;
  color: #333;
}

.form-submit {
  width: 360px;
  padding: 16px;
  margin: 10px 0;
  border: 0;
  outline: 0;

  font-family: "Roboto", sans-serif;
  font-weight: 700;
  font-size: 18px;
  color: #f2f2f2;

  border-radius: 2px;
  background: #84e;
  cursor: pointer;
  transition: ease-in-out 0.3s;
}

.form-submit:hover {
  background: #85e;
}
</style>