
<template>
    <div>
      <main> 
          <div v-if="$route.params.id > 0">
              <div class="" v-for="item in AlumnosDaw" :key="item.id">
                      <div v-if="item.id == $route.params.id">
                          <DetalleAlumno :persona="item"/>
                      </div>
              </div>
              <div class="" v-for="item in ProfesoresDaw2" :key="item.id">
                      <div v-if="item.id == $route.params.id">
                          <DetalleAlumno :persona="item"/>
                      </div>
              </div>
          </div>
          <div v-else>
              <div class="row">
                <div class="col-12 text-center bg-secondary pt-3 pb-3">
                    <h1 class="text-white"> Desarollo de aplicaciones web (DAW) - 2022/2023</h1>
                </div>
              </div>
              <div class="fondo">
                  <div class="row p-0">
                      <h1 class="pt-4 pb-5 text-center"> Profesores</h1>
                      <div class="d-flex justify-content-center">
                          <div v-for="item in ProfesoresDaw" :key="item.id">
                              <fichaProfesor v-if="item.funcion == 'profesor'" :persona="item"/>
                          </div>
                      </div>
                      <h1 class="pt-5 pb-5 text-center">Alumnos</h1>
                      <div class="d-flex justify-content-center pb-5">
                          <div v-for="item in AlumnosDaw" :key="item.id">
                              <div v-if="item.funcion == 'alumno'">
                                  <fichaAlumno :persona="item"/>
                              </div>
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </main> 
    </div>
</template>

<script>
import fichaProfesor from '../components/fichaProfesor.vue'
import fichaAlumno from '../components/fichaAlumno.vue'
import DetalleAlumno from '../components/DetalleAlumno.vue';

export default {
    name: 'Anuario',
    components:{
    fichaAlumno,
    fichaProfesor,
    DetalleAlumno
},
    // Los datos son las variables
    data(){
        return{
            ProfesoresDaw: [
               
                {
                    id:1,
                    nombre: 'Carlos Arrebola',
                    photo: 'carlos.png',
                    funcion: 'profesor'
                },
                {
                    id:2,
                    nombre: 'Patricia Salinas',
                    photo: 'patricia.jpg',
                    funcion: 'profesor'
                },
                 {
                    id:3,
                    nombre: 'Jordi Egea',
                    photo: 'jordi.png',
                    funcion: 'profesor'
                },
                
                {
                    id:4,
                    nombre: 'Ana Rovira',
                    photo: 'ana.jpg',
                    funcion: 'profesor'
                }
                ,{
                    id:5,
                    nombre: 'Raul Sachez',
                    photo: 'raul.jpg',
                    funcion: 'profesor'
                }
            ],
            AlumnosDaw: [
                {
                    id:6,
                    nombre: 'Nicolas BARRIO',
                    photo: 'NICO.png',
                    funcion: 'alumno',
                    estudios:['Grado medio de sistemas microinformaticos y redes','Grado superior de Desarrollo de Aplicaciones Web']
                },
                {
                    id:7,
                    nombre: 'Sergio Pereira',
                    photo: 'sergio.png',
                    funcion: 'alumno',
                    estudios:['Grado medio de sistemas microinformaticos y redes','Grado superior de Desarrollo de Aplicaciones Web'],
                    trabajo:['DJ']
                },
                {
                    id:8,
                    nombre: 'Fran Montañez',
                    photo: 'fran.JPG',
                    funcion: 'alumno',
                    estudios:['Grado medio de sistemas microinformaticos y redes','Grado superior de Desarrollo de Aplicaciones Web']
                },
                {
                    id:9,
                    nombre: 'Pau Diaz',
                    photo: 'pau.png',
                    funcion: 'alumno',
                    estudios:['Grado medio de sistemas microinformaticos y redes','Grado superior de Desarrollo de Aplicaciones Web']
                },
                {
                    id:10,
                    nombre: 'Jose luis Viri',
                    photo: 'viri.jpg',
                    funcion: 'alumno',
                    estudios:['Grado medio de sistemas microinformaticos y redes','Grado superior de Desarrollo de Aplicaciones Web']
                }
            ]
        }
    }
}
</script>