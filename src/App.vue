<template>
  <div id="app">
    <b-button v-b-modal.meu-modal>Abrir Modal</b-button>
    <!-- <b-button v-b-modal="'meu-modal'">Abrir Modal</b-button> -->

    <!-- primeiro exemplo -->
    <!-- <b-modal id="meu-modal" title="BootstrapVue">Olá mundo, eu sou um modal!</b-modal> -->
    





    <!-- exemplo com refs -->
    <!-- <b-button @click="abrirModal">Abrir Modal</b-button>
    <b-modal ref="meu_modal">Modal de teste</b-modal> -->






    <!-- personalizando o tamanho -->
    <!-- <b-modal size="xl" id="meu-modal">Modal gigante!</b-modal> -->
    <!-- <b-modal size="lg" id="meu-modal">Modal grande!</b-modal> -->
    <!-- <b-modal size="sm" id="meu-modal">Modal pequeno!</b-modal> -->






    <!-- alinhando ao centro -->
    <!-- <b-modal centered id="meu-modal">Modal Centralizado</b-modal> -->






    <!-- personalizando as cores -->
    <!-- <b-modal
      id="meu-modal"
      title="Modal Variants"
      header-bg-variant="dark"
      header-text-variant="light"
      body-bg-variant="light"
      body-text-variant="dark"
      footer-bg-variant="danger"
      footer-text-variant="dark"
    >
      <b-container fluid>
        Exemplo de modal com cores personalizadas
      </b-container>
 
      <template v-slot:modal-footer>
        <div class="w-100">
          <p class="float-left">Modal Footer Content</p>
          <b-button
            variant="primary"
            size="sm"
            class="float-right"
            @click="show=false"
          >
            Close
          </b-button>
        </div>
      </template>
    </b-modal> -->








    <!-- cabeçalho e rodapé personalizado via slot -->
    <!-- <b-modal id="meu-modal">
        <template v-slot:modal-header="{ close }">
          <b-button size="sm" variant="outline-danger" @click="close()">
            Fechar Modal
          </b-button>
          <h5>Cabeçalho do modal</h5>
        </template>
 
        <p> Aqui temos o conteúdo do modal </p>
 
        <template v-slot:modal-footer="{ hide , ok }">
          <p>Rodapé personalizado</p>
          <b-button size="sm" variant="outline-danger" @click="hide()">
            Fechar
          </b-button>
          <b-button size="sm" variant="outline-primary" @click="ok()">
            Próximo
          </b-button>
        </template>
    </b-modal> -->

    
    
    



    
    <!-- exemplo prático -->
    <b-table striped hover :items="items" :fields="fields">
      <template v-slot:cell(actions)="data">
        <b-button @click="excluirRegistro(data)" size="sm" variant="danger">Remover</b-button>
      </template>
    </b-table>

    <b-modal ref="modalExcluir">
        <p> Tem certeza que deseja remover esse registro? </p>
 
        <template v-slot:modal-footer="{ hide , ok }">
          <b-button size="sm" variant="danger" @click="hide()">
            Não
          </b-button>
          <b-button size="sm" variant="primary" @click="ok()">
            Sim
          </b-button>
        </template>
    </b-modal>


  </div>
</template>

<script>
  export default {
    // methods: {
      // abrirModal() {
      //   this.$refs['meu_modal'].show()
      // },
      // abrirModal() {
      //   this.$refs.meu_modal.show()
      // },
    // }



    data() {
      return {
        items: [
          { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
          { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
          { age: 89, first_name: 'Geneva', last_name: 'Wilson' },
          { age: 38, first_name: 'Jami', last_name: 'Carney' }
        ],
        fields: [
          {
            key: 'first_name',
            label: 'Nome'
          },
          {
            key: 'last_name',
            label: 'Sobrenome'
          },
          {
            key: 'actions',
            label: 'Ações'
          },
        ]
      }
    },
    methods: {
      excluirRegistro(){
        this.$refs.modalExcluir.show();
      }
    }
  }
</script>