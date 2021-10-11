<template>
    <div>
      <header id="header">
      <div class="container">
        <div id="logo" class="pull-left">
          <a><img src="@/assets/logo.png" /><a id="titulo">Aguacate web</a></a>
        </div>
        <nav id="Contenedor-menu">
          <ul class="Menu-Navegacion">
            <router-link to="/">Inicio</router-link>
            <router-link to="/nosotros">Nosotros</router-link>
            <router-link to="/trabaja-con-nosotros">Trabaja con Nosotros</router-link>
            <router-link to="/contacto">Contáctanos</router-link>
            <li class="menu-has-children">
              <router-link to="/login">Iniciar Sesión</router-link>
            </li>
          </ul>
        </nav>
      </div>
    </header>
    <section id="contacto" class="">
    <div class="container">
      <div class="">
        <div id="Titulo-Contacto">
          <h2 class="">CONTACTA CON NOSOTROS</h2>
          <p class="">Llena el siguiente formulario y nos pondremos<br>en contacto lo mas pronto posible.</p>
        </div>
        <br>
        <br>
        <div class="">
          <div class="contact-form">
            <form action="" method="post" role="form" class="contactForm">
              <div class="col-md-6 padding-right-zero">
                <div class="form-group">
                  <input type="text" name="name" class="form-control" id="name" placeholder="Nombre" data-rule="minlen:4"  />
                </div>
              </div>
              <div class="col-md-6">

                <div class="form-group">
                  <input type="email" class="form-control" name="email" id="email" placeholder="Correo electronico" data-rule="email"/>
                </div>

              </div>
              <div class="col-md-12">
                <div class="form-group">
                  <input type="text" class="form-control" name="Asunto" id="Asunto" placeholder="Asunto" data-rule="minlen:4"  />
                </div>
              </div>
              <div class="col-md-12">
                <div class="form-group">
                  <textarea class="form-control" name="Mensaje" placeholder="Mensaje"></textarea>
                </div>
                <button type="submit" class="btn btn-primary btn-submit">ENVIAR</button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <footer class="footer">
    <div >
      <div>
        <div>
          <small>Copyright ©&nbsp;1999-2021 Aguacate web Colombia LTDA.</small>
          <nav>
            <a href="Nosotros.html">Trabaja con nosotros</a>
            <a href="https://www.sic.gov.co/">www.sic.gov.co</a>
          </nav>
        </div>
        <p>Carrera 5 Numero 02 - 32 Piso 1, Andalucia-valle del cauca, Colombia</p>
      </div>
    </div>
    <div>
      <a href="https://www.sic.gov.co/" target="_blank" rel="nofollow">
        <img width="141" height="30" decoding="async" src="https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/sic.png" alt="SIC - Industria y comercio" srcset="https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/sic@2x.png 2x"></a>
        <a href="https://www.sic.gov.co/pare-y-compare" target="_blank" rel="nofollow">
          <img width="200" height="34" decoding="async" src="https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/pum.png" alt="Precio por unidad de medida" srcset="https://http2.mlstatic.com/ui/navigation/5.16.1/mercadolibre/pum@2x.png 2x"></a>
        </div>
      </footer>
    </div>
</template>
<script>
export default {
    name:'ContactoPage',
}
</script>
<style scoped>
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
html{
  height: 100%;
}
.Login{
  margin: 50px auto;
  width: 400px;
  padding: 30px;
  background: rgba(0,0,0, .7);
  border-radius: 10px;
}
.Login h2{
  margin: 0 0 30px;
  padding: 0;
  font-size: 30px;
  color:white;
  text-align: center;
}
.Login .element label{
  color: #fff;
}
.Login .element input{
  width: 100%;
  padding: 10px 0;
  color: #fff;
  background: transparent;
  border: none;
  border-bottom: 1px solid #fff;
  margin-bottom: 30px;
}
.Login .element input[type="submit"]{
  background-color: #03C4EB;
  border:none;
  letter-spacing: 5px;
  text-transform: uppercase;
  cursor: pointer;
  padding: 15px;
}

#Nosotros {
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
  flex-wrap: wrap;
  -webkit-flex-wrap: wrap;
  -moz-flex-wrap: wrap;
  background: #e6e6e6;
  width: 100%;
  justify-content: center;
  height:500px
}
#Nosotros .TextoNosotros .TituloNosotros {
  margin-bottom: 30px;
  color: black;
  font-style: italic;
  font-weight: 300;
  position: relative;
  padding-bottom: 30px;

}

/*barra largo*/
#Nosotros .TextoNosotros .TituloNosotros:after {
  content: "";
  position: absolute;
  bottom: 0;
  width: 40px;
  height: 2px;
  left: 50%;
  background: #4bf529;
  margin-left: -20px;
}

#contacto
{
    background-color: white;
}
.btn-submit, .btn-submit:hover, .btn-submit:focus
{
    background-color: #03C4EB;
    color: white;
    font-weight: 400;
    font-size: 14px;
    padding: 6px 20px;
}

.loction-info p
{
    margin-bottom: 25px;
}
.loction-info p i
{
    color: #be9e21;
}
#Titulo-Contacto{
  text-align:center;
  color:black;
}

.footer{
  text-align:center;
  color:white;
  background: rgba(0,0,0, .7);
  position: relative;
}
.content-select select {
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}
/* Eliminamos la fecha que por defecto aparece en el desplegable */
.content-select select::-ms-expand {
  display: none;
}
.content-select {
  max-width: 250px;
  position: relative;
}

.content-select select {
  display: inline-block;
  width: 133%;
  cursor: pointer;
  padding: 5px 10px;
  height: 42px;
  outline: 0;
  border: 0;
  border-radius: 0;
  background: rgba(0, 0, 0, 0.2);
  font-size: 1em;
  color: white;
  font-family: "Quicksand", sans-serif;
  border: 2px solid rgba(0, 0, 0, 0.2);
  border-radius: 12px;
  position: relative;
  transition: all 0.25s ease;
}

#titulo{
  color: white;
}
#titulo hover{
  display: none;

}

@media (min-width: 992px) {
  .m-lg-0 {
    margin: 0 !important;
  }
  .mt-lg-0,
  .my-lg-0 {
    margin-top: 0 !important;
  }
  .mr-lg-0,
  .mx-lg-0 {
    margin-right: 0 !important;
  }
  .mb-lg-0,
  .my-lg-0 {
    margin-bottom: 0 !important;
  }
  .ml-lg-0,
  .mx-lg-0 {
    margin-left: 0 !important;
  }
  .m-lg-1 {
    margin: 0.25rem !important;
  }
  .mt-lg-1,
  .my-lg-1 {
    margin-top: 0.25rem !important;
  }
  .mr-lg-1,
  .mx-lg-1 {
    margin-right: 0.25rem !important;
  }
  .mb-lg-1,
  .my-lg-1 {
    margin-bottom: 0.25rem !important;
  }
  .ml-lg-1,
  .mx-lg-1 {
    margin-left: 0.25rem !important;
  }
  .m-lg-2 {
    margin: 0.5rem !important;
  }
  .mt-lg-2,
  .my-lg-2 {
    margin-top: 0.5rem !important;
  }
  .mr-lg-2,
  .mx-lg-2 {
    margin-right: 0.5rem !important;
  }
  .mb-lg-2,
  .my-lg-2 {
    margin-bottom: 0.5rem !important;
  }
  .ml-lg-2,
  .mx-lg-2 {
    margin-left: 0.5rem !important;
  }
  .m-lg-3 {
    margin: 1rem !important;
  }
  .mt-lg-3,
  .my-lg-3 {
    margin-top: 1rem !important;
  }
  .mr-lg-3,
  .mx-lg-3 {
    margin-right: 1rem !important;
  }
  .mb-lg-3,
  .my-lg-3 {
    margin-bottom: 1rem !important;
  }
  .ml-lg-3,
  .mx-lg-3 {
    margin-left: 1rem !important;
  }
  .m-lg-4 {
    margin: 1.5rem !important;
  }
  .mt-lg-4,
  .my-lg-4 {
    margin-top: 1.5rem !important;
  }
  .mr-lg-4,
  .mx-lg-4 {
    margin-right: 1.5rem !important;
  }
  .mb-lg-4,
  .my-lg-4 {
    margin-bottom: 1.5rem !important;
  }
  .ml-lg-4,
  .mx-lg-4 {
    margin-left: 1.5rem !important;
  }
  .m-lg-5 {
    margin: 3rem !important;
  }
  .mt-lg-5,
  .my-lg-5 {
    margin-top: 3rem !important;
  }
  .mr-lg-5,
  .mx-lg-5 {
    margin-right: 3rem !important;
  }
  .mb-lg-5,
  .my-lg-5 {
    margin-bottom: 3rem !important;
  }
  .ml-lg-5,
  .mx-lg-5 {
    margin-left: 3rem !important;
  }
  .p-lg-0 {
    padding: 0 !important;
  }
  .pt-lg-0,
  .py-lg-0 {
    padding-top: 0 !important;
  }
  .pr-lg-0,
  .px-lg-0 {
    padding-right: 0 !important;
  }
  .pb-lg-0,
  .py-lg-0 {
    padding-bottom: 0 !important;
  }
  .pl-lg-0,
  .px-lg-0 {
    padding-left: 0 !important;
  }
  .p-lg-1 {
    padding: 0.25rem !important;
  }
  .pt-lg-1,
  .py-lg-1 {
    padding-top: 0.25rem !important;
  }
  .pr-lg-1,
  .px-lg-1 {
    padding-right: 0.25rem !important;
  }
  .pb-lg-1,
  .py-lg-1 {
    padding-bottom: 0.25rem !important;
  }
  .pl-lg-1,
  .px-lg-1 {
    padding-left: 0.25rem !important;
  }
  .p-lg-2 {
    padding: 0.5rem !important;
  }
  .pt-lg-2,
  .py-lg-2 {
    padding-top: 0.5rem !important;
  }
  .pr-lg-2,
  .px-lg-2 {
    padding-right: 0.5rem !important;
  }
  .pb-lg-2,
  .py-lg-2 {
    padding-bottom: 0.5rem !important;
  }
  .pl-lg-2,
  .px-lg-2 {
    padding-left: 0.5rem !important;
  }
  .p-lg-3 {
    padding: 1rem !important;
  }
  .pt-lg-3,
  .py-lg-3 {
    padding-top: 1rem !important;
  }
  .pr-lg-3,
  .px-lg-3 {
    padding-right: 1rem !important;
  }
  .pb-lg-3,
  .py-lg-3 {
    padding-bottom: 1rem !important;
  }
  .pl-lg-3,
  .px-lg-3 {
    padding-left: 1rem !important;
  }
  .p-lg-4 {
    padding: 1.5rem !important;
  }
  .pt-lg-4,
  .py-lg-4 {
    padding-top: 1.5rem !important;
  }
  .pr-lg-4,
  .px-lg-4 {
    padding-right: 1.5rem !important;
  }
  .pb-lg-4,
  .py-lg-4 {
    padding-bottom: 1.5rem !important;
  }
  .pl-lg-4,
  .px-lg-4 {
    padding-left: 1.5rem !important;
  }
  .p-lg-5 {
    padding: 3rem !important;
  }
  .pt-lg-5,
  .py-lg-5 {
    padding-top: 3rem !important;
  }
  .pr-lg-5,
  .px-lg-5 {
    padding-right: 3rem !important;
  }
  .pb-lg-5,
  .py-lg-5 {
    padding-bottom: 3rem !important;
  }
  .pl-lg-5,
  .px-lg-5 {
    padding-left: 3rem !important;
  }
  .m-lg-auto {
    margin: auto !important;
  }
  .mt-lg-auto,
  .my-lg-auto {
    margin-top: auto !important;
  }
  .mr-lg-auto,
  .mx-lg-auto {
    margin-right: auto !important;
  }
  .mb-lg-auto,
  .my-lg-auto {
    margin-bottom: auto !important;
  }
  .ml-lg-auto,
  .mx-lg-auto {
    margin-left: auto !important;
  }
}

a:hover {
    text-decoration: none;
}

h3.tittle-w3layouts {
    color: #353434;
    font-size: 3em;
    text-align: left;
    letter-spacing: 1px;
    font-weight: 400;
    text-shadow: 0 2px 12px rgba(0, 0, 0, 0.14);
}
#contacto
{
    background-color: white;
}
.btn-submit, .btn-submit:hover, .btn-submit:focus
{
    background-color: #03C4EB;
    color: white;
    font-weight: 400;
    font-size: 14px;
    padding: 6px 20px;
}

.loction-info p
{
    margin-bottom: 25px;
}
.loction-info p i
{
    color: #be9e21;
}
#Titulo-Contacto{
  text-align:center;
  color:black;
}

.footer{
  text-align:center;
  color:white;
  background: rgba(0,0,0, .7);
  position: relative;
}
.content-select select {
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}
/* Eliminamos la fecha que por defecto aparece en el desplegable */
.content-select select::-ms-expand {
  display: none;
}
.content-select {
  max-width: 250px;
  position: relative;
}

.content-select select {
  display: inline-block;
  width: 133%;
  cursor: pointer;
  padding: 5px 10px;
  height: 42px;
  outline: 0;
  border: 0;
  border-radius: 0;
  background: rgba(0, 0, 0, 0.2);
  font-size: 1em;
  color: white;
  font-family: "Quicksand", sans-serif;
  border: 2px solid rgba(0, 0, 0, 0.2);
  border-radius: 12px;
  position: relative;
  transition: all 0.25s ease;
}
</style>