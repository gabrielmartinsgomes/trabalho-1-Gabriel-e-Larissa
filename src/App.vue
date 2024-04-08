<script setup>
import { ref } from 'vue'
const nome = ref('')
const email = ref('')
const senha = ref('')
const confirmar = ref('')
const nascimento = ref('')
const endereço = ref('')
const cidade = ref('')
const estado = ref('')
const hobbies = ref([])
const bio = ref('')
const mostrarResultado = ref(false)
</script>

<template>
  <div class="container">
    <form @submit.prevent="mostrarResultado = !mostrarResultado">
      <div>
        <p>Nome:<input type="text" v-model="nome" placeholder="João" /></p>
        <p>
          Data de nascimento:
          <input type="text" v-model="nascimento" placeholder="00/00/0000" />
        </p>
      </div>
      <div>
        <p>
          E-mail:
          <input type="email" v-model="email"  placeholder="example@example" />
        </p>
        <p>
          Senha:
          <input type="password" v-model="senha" placeholder="********" minlength="3" />
        </p>
        <p>
          Confirme sua Senha:
          <input type="password" v-model="confirmar" placeholder="********" />
        </p>
        <p v-if="confirmar == senha && confirmar != ''">A senha está correta</p>
      </div>
      <div>
        <p>
          Endereço:
          <input type="text" v-model="endereço" placeholder="Rua XXX" />
        </p>
        <p>
          Cidade:
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
          <option value="RN">Rio Grande do Norte</option>
          <option value="RS">Rio Grande do Sul</option>
          <option value="RO">Rondônia</option>
          <option value="RR">Roraima</option>
          <option value="SC">Santa Catarina</option>
          <option value="SE">Sergipe</option>
          <option value="TO">Tocantins</option>
        </select>
      </div>
      <div class="hobbies">
        <label for="hobbies">Hobbies favoritos: </label>
        <div class="sla">
          <input type="checkbox" v-model="hobbies" value="esportes" />
          <p>Esportes</p>
        </div>
        <div class="sla">
          <input type="checkbox" v-model="hobbies" value="ler" />
          <p>Ler</p>
        </div>
        <div class="sla">
          <input type="checkbox" v-model="hobbies" value="musica" />
          <p>Ouvir música</p>
        </div>
        <div class="sla">
          <input type="checkbox" v-model="hobbies" value="videogames" />
          <p>Jogar Videogames</p>
        </div>
        <div class="sla">
          <input type="checkbox" v-model="hobbies" value="assistir" />
          <p>Assistir TV/Série</p>
        </div>
        <div class="sla">
          <input type="checkbox" v-model="hobbies" value="redes" />
          <p>Usar redes sociais</p>
        </div>
      </div>
      <div>
        <p>
          Fale um pouco sobre você:
          <input type="text" v-model="bio" placeholder="Eu..." />
        </p>
      </div>
      <div>
        <button type="submit">Mostrar</button>
      </div>
      
    </form>
    <div v-if="mostrarResultado" class="resultado">
        <h2>Resultado</h2>
        <p>Nome: {{ nome }}</p>
        <p>Email: {{ email }}</p>
        <p>Senha: {{ senha }}</p>
        <p>Nascimento: {{ nascimento }}</p>
        <p>Endereço: {{ endereço }}</p>
        <p>Cidade: {{ cidade }}</p>
        <p>Estado: {{ estado }}</p>
        <p>Hobbies: {{ hobbies }}</p>
        <p>Biografia: {{ bio }}</p>
        <p>{{ mostrarResultado }}</p>
      </div>
  </div>
</template>
<style scoped>
form {
  background-color: black;
  color: white;
  display: flex;
  box-sizing: border-box;
  padding: 30px;
  width: 100vw;
}

form > * {
  margin: 20px;
}

div {
  padding: 10px;
}
.hobbies {
  margin: 25px;
  display: block;
}

.sla {
  display: flex;
  gap: 10px;
}
</style>
