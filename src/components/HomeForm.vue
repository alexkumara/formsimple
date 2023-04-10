<template>
    <div class="container">
        <div class="py-5 text-center">
            <h1>Formulir Pendaftaran</h1>
        </div>
        <div class="col-md-12">
            <form>
                <div class="row">
                    <div class="col-md-6 mb-3">
                        <label class="form-label">Nama Lengkap</label> <br>
                        <input type="text" class="form-control" placeholder="Masukkan Nama Lengkap" v-model="form.fullName" />
                    </div>
                    <div class="col-md-6 mb-3">
                        <label class="form-label">Email</label>
                        <div class="input-group">
                             <div class="input-group-prepend">
                            <span class="input-group-text">@</span>
                        </div>
                        <input type="text" class="form-control" placeholder="Masukkan Email" v-model="form.email" />
                        </div>
                    </div>
                </div>
                <div class="mb-3">
                    <label class="form-label">Alamat Lengkap</label> <br>
                    <textarea class="form-control" placeholder="Contoh: Jl.doang jadian kagak" rows="3" v-model="form.adress" ></textarea>
                </div>
                
                <div class="d-grid gap-2 col-2 mx-auto">
                    <button class="btn btn-primary" v-on:click="tampilkan" type="button">Submit</button>
                </div>
            
                
                <table class="table table-striped" id="tampilkan">
                    <h4 class="mb-3">User Data</h4>
                    <tr>
                        <th>Nama Lengkap</th>
                        <th>Email</th>
                        <th>Alamat</th>
                    </tr>
                    <tr>
                        <td>{{ form.fullName }}</td>
                        <td>{{ form.email }}</td>
                        <td>{{ form.adress }}</td>
                    </tr>
                </table>
            </form>
        </div>
            
    </div>
    </template>
    
    <script>
    export default {
        data() {
            return {
                form:{
                    fullName: '',
                    email: '',
                    adress: ''
                }
            }
        },
        methods: {
            tampilkan () {
                document.getElementById('tampilkan').style.display="block"
                console.warn(this.form)
            }
        }
    }
    </script>
    
    <style scoped>
        #tampilkan {
            display: none;
            display: 0px;
        }
        .table {
            width:100%;
        }
    </style>