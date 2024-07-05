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
      <div v-if="!mostrarResultado">
        <p>Nome:<input type="text" v-model="nome" placeholder="João" /></p>
        <p>
          Data de nascimento:
          <input type="number" v-model="nascimento" placeholder="00/00/0000" />
        </p>
        <p>
          E-mail:
          <input type="email" v-model="email" placeholder="example@example" />
        </p>
        <p>
          Senha:
          <input type="password" v-model="senha" placeholder="********" minlength="4" />
        </p>
        <p>
          Confirme sua Senha:
          <input type="password" v-model="confirmar" placeholder="********" minlength="4" />
        </p>
        <p id="verde" v-if="confirmar == senha && confirmar != ''">A senha está correta</p>
        <p id="vermelho" v-if="confirmar != senha && confirmar != ''">A senha está incorreta</p>
        <p>
          Endereço:
          <input type="text" v-model="endereço" placeholder="Rua XXX" />
        </p>
        <p>
          Cidade:
          <input type="text" v-model="cidade" placeholder="Joinville" />
        </p>
        <p>
          Fale um pouco sobre você:
          <input type="text" v-model="bio" placeholder="Eu..." />
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
        <button type="submit">Mostrar</button>

        <div class="hobbies">
          <label for="hobbies">Hobbies favoritos: </label>
          <div class="sla">
            <input type="checkbox" v-model="hobbies" value="Esportes" />
            <p>Esportes</p>
          </div>
          <div class="sla">
            <input type="checkbox" v-model="hobbies" value="Ler" />
            <p>Ler</p>
          </div>
          <div class="sla">
            <input type="checkbox" v-model="hobbies" value="Música" />
            <p>Ouvir música</p>
          </div>
          <div class="sla">
            <input type="checkbox" v-model="hobbies" value="Videogames" />
            <p>Jogar Videogames</p>
          </div>
          <div class="sla">
            <input type="checkbox" v-model="hobbies" value="Assistir" />
            <p>Assistir TV/Série</p>
          </div>
          <div class="sla">
            <input type="checkbox" v-model="hobbies" value="Redes" />
            <p>Usar redes sociais</p>
          </div>
          <div class="sla">
            <input type="checkbox" v-model="hobbies" value="Outros" />
            <p>Outros</p>
          </div>
        </div>
      </div>

      <div v-if="mostrarResultado">
        <h2>Resultado</h2>
        <p>Nome: {{ nome }}</p>
        <p>Email: {{ email }}</p>
        <p>Senha: {{ senha }}</p>
        <p>Nascimento: {{ nascimento }}</p>
        <p>Endereço: {{ endereço }}</p>
        <p>Cidade: {{ cidade }}</p>
        <p>Estado: {{ estado }}</p>
        <p>Hobbies: {{ hobbies.join(', ') }}</p>
        <p>Biografia: {{ bio }}</p>
        <button type="submit">Voltar</button>
      </div>
    </form>
  </div>
</template>
