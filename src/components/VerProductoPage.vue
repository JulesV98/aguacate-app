<template>
    <div>
        <header id="header">
            <div class="container">
                <div id="logo" class="pull-left">
                <a><img src="@/assets/logo.png" /><a id="titulo">Aguacate web</a></a>
                </div>
                <nav id="Contenedor-menu">
                <ul class="Menu-Navegacion">
                <router-link to="/registro-producto">Publicar</router-link>
                <router-link to="/ver-producto">Mis productos</router-link>
                <router-link to="/panel-usuario">Perfil</router-link>
                <li class="menu-has-children">
                <router-link to="/">Cerrar Sesión</router-link>
                </li>
                </ul>
                </nav>
            </div>
        </header>
        <div class="container">
          <b-alert 
          :show="dismissCountDown" 
          dismissible
          variant="mensaje.color" 
          @dismissed="dismissCountDown=0"
          @dismiss-count-down="countDownChanged" >
          {{mensaje.texto}} 
          </b-alert>
          <br />
            <h1>Lista de productos</h1>
            <br />
            <form @submit.prevent="editarProducto(productoEditar)" v-if="editar" >
                <h3>Editar producto</h3>

                <input type="text" class="form-control my-2" placeholder="Nombre" v-model="productoEditar.nombre">
                <input type="text" class="form-control my-2" placeholder="Descripcion" v-model="productoEditar.descripcion">
                <input type="text" class="form-control my-2" placeholder="Descripcion" v-model="productoEditar.precio">
                <b-button class="btn-success my-2 mx-2" type="submit">Actualizar</b-button>
                <b-button class=" my-2" type="submit" @click="editar=false">Cancelar</b-button>

            </form>
            <br />

            <table class="table">
                <thead>
                    <tr>
                        <!-- <th scope="col">#</th> -->
                        <th scope="col">Producto</th>
                        <th scope="col">Descripcion</th>
                        <th scope="col">Precio(x Lb.)</th>
                        <th scope="col">Acciones</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(item, index) in productos" :key="index">
                        <td>{{item.nombre}}</td>
                        <td>{{item.descripcion}}</td>
                        <td>{{item.precio}}</td>
                        <td>
                            <b-button class="boton_personalizado" @click="eliminarProducto(item._id)">Eliminar</b-button>
                            <b-button class="boton_personalizado1" @click="activarEdicion(item._id)">Editar</b-button>
                        </td>
                    </tr>

                </tbody>
            </table>

        </div>
    </div>
</template>
<script>
export default {
    name:'VerProductoPage',
    data() {
        return {

            productos: [],
            mensaje: {color: 'success', texto: ''}, 
            dismissSecs: 0, 
            dismissCountDown: 0,

            producto:{_id:"",nombre:"",descripcion:"",precio:""},
            editar:false,
            notaEditar:{}

        }

    },

    created() {

        this.listarProductos();

    },

    methods: {

        listarProductos() {

            this.axios.get('/producto')
                .then(res => {
                    console.log(res.data);
                    this.productos = res.data;

                })
                .catch(e => {

                    console.log(e.response);

                })

        },

        eliminarProducto(id){

            this.axios.delete(`/producto/${id}`)
            .then(res=>{

                const index = this.notas.findIndex(item=> item._id===res.data._id);
                this.notas.splice(index, 1);
                this.mensaje.color="success";
                this.mensaje.texto="Producto Eliminado";
                this.showAlert();


            })
            .catch(e=>{

                  console.log(e.response);

            })
        },

        activarEdicion(id){

            this.editar=true;
            this.axios.get(`/producto/${id}`)
            .then(res=>{

                this.productoEditar=res.data;

            })
            .catch(e=>{

                 console.log(e.response);


            })


        },

        editarProducto(item){
            
            this.axios.put(`/producto/${item._id}`, item)
            .then(res=>{
                const index= this.productos.findIndex(n=> n._id===res.data._id);
                this.productos[index].nombre=res.data.nombre;
                this.productos[index].descripcion=res.data.descripcion;
                this.productos[index].precio=res.data.precio;
                this.mensaje.color="success";
                this.mensaje.texto="Producto Editado";
                this.showAlert();
                this.editar=false;


            })
            .catch(e=>{

                console.log(e.response);

            })



        },
        countDownChanged(dismissCountDown) { 
            this.dismissCountDown = dismissCountDown 
        }, 
        showAlert() { 
            this.dismissCountDown = this.dismissSecs 
        }

    }
}
</script>
<style>
#titulo{
  color: white;
}
#titulo hover{
  display: none;

}
/*--------------------------------------------------------------
# General
--------------------------------------------------------------*/
body {
  background: #fff;
  color: #666666;
  font-family: "Open Sans", sans-serif;
}

/*--------------------------------------------------------------
# HEADER
--------------------------------------------------------------*/
#header {
  background: #111;
  padding: 20px 0;
  height: 90px;
}

#header #logo {
  float: left;
}

#header #logo img {
  padding: 0;
  margin: 0;
  max-height: 50px;
}

.is-sticky #header {
  background: rgba(0, 0, 0, 0.85);
}


/*--------------------------------------------------------------
# MENU DE NAVEGACION
--------------------------------------------------------------*/
.Menu-Navegacion, .Menu-Navegacion * {
  margin: 0;
  padding: 0;
  list-style: none;
}

.Menu-Navegacion ul {
  position: absolute;
  display: none;
  top: 100%;
  left: 0;
  z-index: 99;
}

.Menu-Navegacion li {
  position: relative;
  white-space: nowrap;
}

.Menu-Navegacion > li {
  float: left;
}

.Menu-Navegacion li:hover > ul,
.Menu-Navegacion li.sfHover > ul {
  display: block;
}

.Menu-Navegacion ul ul {
  top: 0;
  left: 100%;
}

.Menu-Navegacion ul li {
  min-width: 180px;
}

.sf-arrows .sf-with-ul {
  padding-right: 30px;
}

#Contenedor-menu {
  float: right;
  margin: 5px 0;
}

.Menu-Navegacion a {
  padding: 10px 15px;
  text-decoration: none;
  display: inline-block;
  color: #fff;
  font-family: 'Raleway', sans-serif;
  font-weight: 300;
  font-size: 14px;
  outline: none;
}

.Menu-Navegacion a:hover, .Menu-Navegacion li:hover > a {
  color: #03C4EB;
}
body {
  color: #404040;
  font-family: "Arial", Segoe UI, Tahoma, sans-serifl, Helvetica Neue, Helvetica;
}

.seccion-perfil-usuario .perfil-usuario-body,
.seccion-perfil-usuario {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  align-items: center;
}

.seccion-perfil-usuario .perfil-usuario-portada {
  display: block;
  position: relative;
  width: 100%;
  height: 13rem;
  border-radius: 0 0 20px 20px;
}

.seccion-perfil-usuario .perfil-usuario-avatar {
  display: flex;
  width: 180px;
  height: 180px;
  align-items: center;
  justify-content: center;
  border: 7px solid #ffffff;
  background-color: #dfe5f2;
  border-radius: 50%;
  box-shadow: 0 0 12px rgba(0, 0, 0, 0.2);
  position: absolute;
  bottom: -40px;
  left: calc(50% - 90px);
  z-index: 1;
}

.seccion-perfil-usuario .perfil-usuario-avatar img {
  width: 100%;
  position: relative;
  border-radius: 50%;
}

.seccion-perfil-usuario .perfil-usuario-body {
  width: 70%;
  position: relative;
  max-width: 750px;
}

.seccion-perfil-usuario .perfil-usuario-body .titulo {
  display: block;
  width: 100%;
  font-size: 1.75em;
  margin-bottom: 0.5rem;
}

.seccion-perfil-usuario .perfil-usuario-body .texto {
  color: #848484;
  font-size: 0.95em;
}

.seccion-perfil-usuario .perfil-usuario-footer,
.seccion-perfil-usuario .perfil-usuario-bio {
  display: flex;
  flex-wrap: wrap;
  padding: 1.5rem 1.7rem;
  box-shadow: 0 0 12px rgba(0, 0, 0, 0.2);
  background-color: #fff;
  border-radius: 15px;
  width: 100%;
}

.seccion-perfil-usuario .perfil-usuario-bio {
  margin-bottom: 1.25rem;
  text-align: center;
}

.seccion-perfil-usuario .lista-datos {
  width: 100%;
  list-style: none;
}

.seccion-perfil-usuario .lista-datos li {
  padding: 5px 0;
}

.seccion-perfil-usuario .lista-datos li > .icono {
  margin-right: 1rem;
  font-size: 1.2rem;
  vertical-align: left;
}

.boton_personalizado{
    text-decoration: none;
    padding:0px;
    margin: 0px;
    border: none;
    font-weight: 200;
    font-size: 20px;
    color: whitesmoke;
    background-color: green;
  }
.boton_personalizado1{
    text-decoration: none;
    padding:0px;
    margin: 0px;
    border: none;
    font-weight: 200;
    font-size: 20px;
    color: black;
    background-color: white;
  }
.boton_personalizado1:hover{
    color: #1883ba;
    background-color: #ffffff;
    text-decoration: none;
  }
.boton_personalizado:hover{
    color: #1883ba;
    background-color: #ffffff;
    text-decoration: none;
  }

.footer {
  text-align: center;
  color: white;
  background: rgba(0, 0, 0, 0.7);
  position: relative;
}

</style>