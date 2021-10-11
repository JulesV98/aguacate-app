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
            <!--==========================
        =            html            =
        ===========================-->
            <section class="seccion-perfil-usuario">
            <div class="perfil-usuario-header">
                <div class="perfil-usuario-portada">
                <div class="perfil-usuario-avatar">
                    <img src="@/assets/FotoPerfil.png"  alt="img-avatar" />
                </div>
                </div>
            </div>
            <br />
            <br />
            <br />
            <br />
            <div class="perfil-usuario-body">
                <div class="perfil-usuario-bio">
                <h3 class="titulo">Nombre de usuario</h3>
                </div>
                <div class="perfil-usuario-footer">
                <ul class="lista-datos">
                    <li><i class=""></i> Nombre: </li>
                    <li><i class=""></i>Apellidos:</li>
                    <li><i class=""></i>Telefono</li>
                    <li><i class=""></i>Correo</li>
                    <li><i class=""></i>Ciudad</li>
                    <li><i class=""></i>Contraseña</li>
                </ul>
                </div>
            </div>
            </section>
            <br />
            <br />
            <br />
            <br />
            <footer class="footer">
            <div>
                <div>
                <div>
                    <small
                    >Copyright ©&nbsp;1999-2021 Aguacate web Colombia LTDA.</small
                    >
                    <nav>
                    <a href="Nosotros.html">Trabaja con nosotros</a>
                    <a href="https://www.sic.gov.co/">www.sic.gov.co</a>
                    </nav>
                </div>
                <p>
                    Carrera 5 Numero 02 - 32 Piso 1, Andalucia-valle del cauca, Colombia
                </p>
                </div>
            </div>
            <div>
                <a href="https://www.sic.gov.co/" target="_blank" rel="nofollow">
                <img
                    width="141"
                    height="30"
                    decoding="async"
                    src="https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/sic.png"
                    alt="SIC - Industria y comercio"
                    srcset="
                    https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/sic@2x.png 2x
                    "
                /></a>
                <a
                href="https://www.sic.gov.co/pare-y-compare"
                target="_blank"
                rel="nofollow"
                >
                <img
                    width="200"
                    height="34"
                    decoding="async"
                    src="https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/pum.png"
                    alt="Precio por unidad de medida"
                    srcset="
                    https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/pum@2x.png 2x
                    "
                /></a>
            </div>
            </footer>

    </div>
</template>

<script>
export default {
    name:'PanelUsuarioPage',
    data() {
        return {

            vendedores: [],

            usuario:{nombre:"",apellido:"",telefono:"",correo:"",ciudad:"",contraseña:""},
            editar:false,
        }

    },

    methods: {

        created() {
        this.verUsuario();
        }, 

        verUsuario(){
            this.axios.get('/usuario')
            .then(res=>{
                console.log(res.data);
                this.vendedores=res.data;

            })
            .catch(e=>{
                console.log(e.response);
            })
        },
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

.footer {
  text-align: center;
  color: white;
  background: rgba(0, 0, 0, 0.7);
  position: relative;
}



</style>