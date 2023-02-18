<template>
  <div class="calculator">
    <div class="top">
      <div class="text">calc</div>
      <div class="switch">
        <div class="theme">THEME</div>
        <div class="switch-button">
          <div class="switch-button-text">
            <span>1</span>
            <span>2</span>
            <span>3</span>
          </div>
          <div class="switch-button-circle">
            <div class=""></div>
          </div>
        </div>
      </div>
    </div>

    <div class="display">
      {{ current || 0 }}
    </div>

    <div class="main-calc">
      <div @click="append('7')" class="char">7</div>
      <div @click="append('8')" class="char">8</div>
      <div @click="append('9')" class="char">9</div>
      <div @click="erase()" class="char">DEL</div>
      <div @click="append('4')" class="char">4</div>
      <div @click="append('5')" class="char">5</div>
      <div @click="append('6')" class="char">6</div>
      <div @click="appendOperator('+')" class="char operator">+</div>
      <div @click="append('1')" class="char">1</div>
      <div @click="append('2')" class="char">2</div>
      <div @click="append('3')" class="char">3</div>
      <div @click="append('-')" class="char operator">-</div>
      <div @click="point()" class="char">.</div>
      <div @click="append('0')" class="char">0</div>
      <div @click="append('/')" class="char operator">/</div>
      <div @click="append('*')" class="char operator">x</div>
      <div @click="reset()" class="char long">RESET</div>
      <div @click="equals()" class="char long operator">=</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      current: "",
      operator: null
    };
  },
  methods: {
    reset() {
      this.current = "";
    },
    append(number) {
      this.current = `${this.current}${number}`;
    },
    point() {
      if (this.current.indexOf(".") === -1) {
        this.append(".");
      }
    },
    equals() {
      this.current = eval(this.current);
    },
    erase() {
      this.current = this.current.slice(0, -1);
    },
    appendOperator(operator) {
      this.operator = operator;
      this.current = `${this.current}`;
    }
  },
};
</script>

<style>
.calculator {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #1e1e1e;
  color: #fff;
  font-family: "Roboto", sans-serif;
  font-size: 1.5rem;
  font-weight: 500;
}

.top {
  width: 100%;
  height: 10%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 1rem;
}

.text {
  font-size: 1.5rem;
  font-weight: 500;
}

.switch {
  display: flex;
  justify-content: center;
  align-items: center;
}

.theme {
  font-size: 1rem;
  font-weight: 500;
  margin-right: 0.5rem;
}

.switch-button {
  width: 3rem;
  height: 1.5rem;
  border-radius: 1rem;
  background-color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 0.2rem;
  cursor: pointer;
}

.switch-button-text {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 100%;
}

.switch-button-text span {
  font-size: 0.8rem;
  font-weight: 500;
}

.switch-button-circle {
  width: 1rem;
  height: 1rem;
  border-radius: 50%;
  background-color: #1e1e1e;
  display: flex;
  justify-content: center;
  align-items: center;
}

.switch-button-circle div {
  width: 0.5rem;
  height: 0.5rem;
  border-radius: 50%;
  background-color: #fff;
}

.display {
  width: 100%;
  height: 20%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 3rem;
  font-weight: 500;
}

.main-calc {
  width: 100%;
  height: 70%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-gap: 0.5rem;
}

.char {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff;
  color: #1e1e1e;
  font-size: 1.5rem;
  font-weight: 500;
  cursor: pointer;
}

.char:hover {
  background-color: #1e1e1e;
  color: #fff;
}

.operator {
  background-color: #1e1e1e;
  color: #fff;
}

.long {
  grid-column: span 2;
}

@media (max-width: 768px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 425px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 375px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 320px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 280px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 240px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 200px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 160px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 120px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 80px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 40px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 20px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 10px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 5px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 1px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

@media (max-width: 0px) {
  .calculator {
    width: 100%;
    height: 100%;
  }
}

</style>