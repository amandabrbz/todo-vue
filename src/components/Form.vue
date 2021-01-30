<template>
  <form>
    <label for="task">
      quais são as tarefas de hoje?
    </label>
    <input type="text" id="task" name="task" autocomplete="off" />
    <button type="submit">
      gravar
    </button>
  </form>
</template>

<script>
export default {
  name: "Form",
};
</script>

<style scoped>
form {
  max-width: 300px;
  margin: 50px auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

label {
  color: #288aac;
  font-size: 1.25rem;
  overflow: hidden;
  border-right: 0.15em solid orange;
  white-space: nowrap;
  margin: 0 auto 10px;
  animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
}

input {
  width: 300px;
  padding: 8px 16px;
  border: 1px solid #4e4b3e;
  border-radius: 24px;
  font-size: 1rem;
}

input::placeholder {
  color: #4f7947;
  font-size: 1rem;
}

input:active,
input:focus {
  color: #232423;
  font-size: 1rem;
  outline: none;
  box-shadow: 0 14px 15px -15px #f0a731cc;
}

button {
  border-radius: 24px;
  padding: 8px 16px;
  margin: 16px auto;
  font-weight: bold;
  border: 2px solid #4f7947;
  outline: none;
  background: #4f7947;
  color: #f0a731;
  font-size: 1rem;
}

button:hover {
  cursor: pointer;
  box-shadow: 11px 7px 38px -17px #000000;
}

button:disabled {
  color: #faf9f5;
  background: #bcc4bc;
  border: 2px solid #bcc4bc;
  cursor: not-allowed;
}

@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}

@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: orange;
  }
}
</style>
