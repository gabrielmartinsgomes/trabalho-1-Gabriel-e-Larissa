<script setup>
import { ref } from 'vue'
const nome = ref('');
const email = ref('');
const senha = ref('');
const confirmar = ref('');
const nascimento = ref('');
const endereço = ref('');
const cidade = ref('');
const estado = ref('');
const hobbies = ref ('');
</script>

<template>
  <form>
    <div>
      <p>
        Nome:<input type="text" v-model="nome" required placeholder="João" />
      </p>
      <p>Data de nascimento:
        <input type="text" v-model="nascimento" placeholder="00/00/0000" />
      </p>
    </div>
    <div>
      <p>E-mail:
        <input type="email" v-model="email" required placeholder="example@example" />
      </p>
      <p>Senha:
        <input type="password" v-model="senha" required placeholder="********" minlength="3" />
      </p>
      <p>Confirme sua Senha:
        <input type="password" v-model="confirmar" required placeholder="********" />
      </p>
      <p v-if="confirmar == senha && confirmar != ''">A senha está correta</p>
      <p> Endereço:
        <input type="text" v-model="endereço" placeholder="Rua XXX" />
      </p>
      <p> Cidade:
        <input type="text" v-model="cidade" placeholder="Joinville" />
      </p>
      <label for="estado">Estado: </label>
  <select v-model="estado">
    <option value="AC">Acre</option>
    <option value="AL">Alagoas</option>
    <option value="AP">Amapá</option>
    <option value="AM">Amazonas</option>
    <option value="BA">Bahia</option>
    <option value="CE">Ceará</option>
    <option value="DF">Distrito Federal</option>
    <option value="ES">Espírito Santo</option>
    <option value="GO">Goiás</option>
    <option value="MA">Maranhão</option>
    <option value="MT">Mato Grosso</option>
    <option value="MS">Mato Grosso do Sul</option>
    <option value="MG">Minas gerais</option>
    <option value="PA">Pará</option>
    <option value="PB">Paraíba</option>
    <option value="PR">Paraná</option>
    <option value="PE">Pernambuco</option>
    <option value="PI">Piauí</option>
    <option value="RJ">Rio de Janeiro</option>
    <option value="RN">Rio Grande do Norte </option>
    <option value="RS">Rio Grande do Sul</option>
    <option value="RO">Rondônia</option>
    <option value="RR">Roraima</option>
    <option value="SC">Santa Catarina</option>
    <option value="SE">Sergipe</option>
    <option value="TO">Tocantins</option>
   
  </select>
  <label for="hobbies">Hobbies favoritas</label>
  <input type="checkbox" v-model="hobbies" value="esportes" /> Esportes
  <input type="checkbox" v-model="hobbies" value="ler" /> Ler
  <input type="checkbox" v-model="hobbies" value="musica" /> Ouvir música

      
      
    </div>
  </form>
</template>
<style scoped>
form {
  background-color: black;
  color: white;
}
</style>
