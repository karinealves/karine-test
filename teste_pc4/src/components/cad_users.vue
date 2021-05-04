<template>
<div class="container">
<h3>CADASTRO DE USUÁRIOS</h3>
<div class="row">
<div class="col">
    <label for="exampleInputEmail1">Nome</label>
    <input type="text" class="form-control" id="name" placeholder="Digite o nome">
  </div>
  <div class="col">
    <label for="exampleInputPassword1">Email</label>
    <input type="email" class="form-control" id="email" placeholder="me@example.com">
  </div>
    <select class="custom-select" >
        <option selected placeholder="Selecione um item">Setor</option>
        <option value="1">Ads</option>
        <option value="2">Architectural Genie</option>
        <option value="3">Branding</option>
        <option value="4">Branding & Marketing</option>
        <option value="5">Design</option>
        <option value="6">Marketing</option>
        <option value="7">Sales</option>
        <option value="8">Social Media</option>
    </select>
    <select class="custom-select">
        <option selected>Cargo</option>
        <option value="1">Account executive</option>
        <option value="2">Brand Manager</option>
        <option value="3">Computer Network Architect</option>
        <option value="4">Copywriting</option>
        <option value="5">Content Manager</option>
        <option value="6">Specialist</option>
        <option value="7">Trainee</option>
        <option value="8">UI|UX</option>

    </select>
    <select class="custom-select">
        <option selected>Função</option>
        <option value="1">Admin</option>
        <option value="2">Editor</option>
    </select>
  <button type="submit" class="btn btn-primary" v-on:click.prevent=saveUser()>Salvar</button>
</div>
</div>

</template>