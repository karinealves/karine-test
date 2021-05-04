<template>
<div class="container">
    <div class="table-responsive">
            <table class="table">
              <thead>
                <tr>
                  <th scope="col">
                    Nome
                  </th>
                  <th>
                    Cargo
                  </th>
                  <th>
                    Status
                  </th>
                  <th>
                    Função
                  </th>
                  <th>

                  </th>
                </tr>
              </thead>
              <tbody>
              <tr v-for="user in teste_pc4" v-bind:key="user.id">
              <template v-if="editId == user.id">
              <td><input v-model="user.id" type="text"></td>
              <td><input v-model="user.name" type="text"></td>
              
              </template>
              <template v-else>
                <td>
                  {{user.id}}
                </td>
                <td>
                  {{user.name}}
                </td>
                <td>
                  {{user.role}}
                </td>
                <td>
                  {{user.occupation}}
                </td>
                <td>
                  {{user.active}}
                </td>
                
                <td>
                  {{user}}
                </td>
              </template>      
              </tr>
              </tbody>
          </table>    
    </div> 

<button type="submit" class="btn btn-primary" v-on:click="onEdit(cad_users)">Novo</button>
</div>

</template>

<script>
export default {
  data(){
    return{
      comments: [],
      id:'',
      name:'',
      email:'',
      department:'',
      occupation:'',
      profile_image:'',
      role:'',
      active:''
    }
  },
  methods:{
    addComment(){
      if(this.id.trim() === '' || this.name.trim() === ''|| this.email.trim() === '' || this.department.trim() === '' || this.occupation.trim() === '' || this.profile_image.trim() === '' || this.role.trim() === '' || this.active.trim() === ''){
        return;
      }
      this.comments.push({
        id: this.id,
        name: this.name,
        email: this.email,
        department: this.department,
        occupation: this.occupation,
        profile_image: this.profile_image,
        role: this.role,
        active: this.active
      });

      this.id = '';
      this.name = '';
      this.email = '';
      this.department = '';
      this.occupation = '';
      this.profile_image = '';
      this.role = '';
      this.active = '';
    }
  },
  
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
nav{
position: fixed;
width: 900px;
height: 150px;
left: 1000px;
top: 2000px;
color: #000;
}
</style>
