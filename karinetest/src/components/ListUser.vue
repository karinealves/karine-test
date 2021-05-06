<template>
<div class="container px-3 px-md-4 px-lg-5">
    
    <div class="row mt-5">
    <div class="col-12 border-bottom mb-5">
      <p class="">CADASTRAR NOVO USUÁRIO</p>
    </div>
      <div class="col-2">
        <label for="">Foto</label>
        <input type="file" class="form-control"  required>
      </div>
      <div class="col-4">
        <label for="">Nome</label>
        <input type="text" class="form-control" placeholder="Digite o nome" v-model="user.name" required> 
      </div>
      <div class="col-4">
        <label for="">CPF</label>
        <input type="text" class="form-control" placeholder="Digite somente números" v-model="user.cpf" required>
      </div>
      <div class="col-4">
        <label for="">Email</label>
        <input type="email" class="form-control" placeholder="me@example.com" v-model="user.email" required>
      </div>
      <div class="form-group col-md-4">
          <label for="">Setor</label>
          <select v-model="user.setor" class="form-control" required>
            <option disabled value="">Selecione um item</option>
                <option>Ads</option>
                <option>Architectural Genie</option>
                <option>Branding</option>
                <option>Branding & Marketing</option>
                <option>Design</option>
                <option>Marketing</option>
                <option>Sales</option>
                <option>Social Media</option>
            <span>Selected: {{ setor }}</span>
            
          </select>
      </div>
      <div class="form-group col-md-4">
          <label for="">Cargo</label>
          <select v-model="user.cargo" class="form-control" required>
            <option disabled value="">Selecione um item</option>
                <option>Account executive</option>
                <option>Brand Manager</option>
                <option>Computer Network Architect</option>
                <option>Copywriting</option>
                <option>Content Manager</option>
                <option>Specialist</option>
                <option>Trainee</option>
                <option>UI|UX</option>
            <span>Selected: {{ cargo }}</span>
          </select>
      </div>    
      <div class="form-group col-md-4">
          <label for="">Função</label>
          <select v-model="user.funcao" class="form-control" required>
            <option disabled value="">Selecione um item</option>
                <option>Admin</option>
                <option>Editor</option>
            <span>Selected: {{ funcao }}</span>
          </select>
      </div>
      <div class="ml-auto text-right">    
          <button type="submit" class="btn btn-primary" v-on:click.prevent="saveUser(user)">Salvar</button>
      </div>
    </div>
    
  </div>
</template>

<script>
export default {
    data() {
        return{
            user: [],
                name: '',
                email: '',
                cpf: '',
                setor: '',
                cargo: '',
                funcao: ''
        }

    },
    methods: {
        saveUser(user) {
            let users = localStorage.getItem('Newusers');

            if(users) {

              //se existir, atualizar meus usuarios no localStorage
              users = JSON.parse(users);
              users.push(user);

            } else {
              
                users = [user];
            }
             localStorage.setItem('Newusers', JSON.stringify(users))   
        }
            
    }
        

  
}

</script>