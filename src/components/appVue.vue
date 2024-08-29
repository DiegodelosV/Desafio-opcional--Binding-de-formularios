<script>
export default {
  name: "appVue",
  data() {
    return {
      usuario: {
        title: "",
        emoji: "",
        apreciacion: "",
        competencias: [],
        opinion: "",
      },
    };
  },
};
</script>

<template>
  <body>
    <div id="app" class="container mt-5">
      <div class="row">
        <div id="form" class="col-md-6">
          <form class="bg-dark text-white p-4 rounded">
            <div class="form-group row border-bottom border-white mb-2">
              <label for="title" class="col-sm-1 col-form-label">Título:</label>
              <div class="col-sm-11">
                <input
                  type="text"
                  id="title"
                  class="form-control mb-3"
                  v-model="usuario.title"
                  placeholder="Título"
                />
              </div>
            </div>

            <div class="form-group row border-bottom border-white">
              <label for="emoji" class="col-sm-1 col-form-label">Emoji:</label>
              <div class="col-sm-11 mb-3">
                <select id="emoji" class="form-select" v-model="usuario.emoji">
                  <option>🧑‍💻</option>
                  <option>👍</option>
                  <option>👎</option>
                  <option>🤔</option>
                  <option>🤩</option>
                  <option>🤯</option>
                  <option>👀</option>
                </select>
              </div>
            </div>

            <div class="form-group row border-bottom border-white mb-2">
              <label class="col-sm-2 col-form-label">Apreciación:</label>
              <div class="col-sm-10 mt-2">
                <div class="form-check form-check-inline">
                  <input
                    class="form-check-input"
                    type="radio"
                    id="regular"
                    value="Regular"
                    v-model="usuario.apreciacion"
                  />
                  <label class="form-check-label" for="regular">Regular</label>
                </div>
                <div class="form-check form-check-inline">
                  <input
                    class="form-check-input"
                    type="radio"
                    id="bien"
                    value="Bien"
                    v-model="usuario.apreciacion"
                  />
                  <label class="form-check-label" for="bien">Bien</label>
                </div>
                <div class="form-check form-check-inline">
                  <input
                    class="form-check-input"
                    type="radio"
                    id="muy_bien"
                    value="Muy bien"
                    v-model="usuario.apreciacion"
                  />
                  <label class="form-check-label" for="muy_bien"
                    >Muy bien</label
                  >
                </div>
                <div class="form-check form-check-inline">
                  <input
                    class="form-check-input"
                    type="radio"
                    id="increible"
                    value="Increíble"
                    v-model="usuario.apreciacion"
                  />
                  <label class="form-check-label" for="increible"
                    >Increíble</label
                  >
                </div>
              </div>
            </div>

            <div class="form-group row border-bottom border-white mb-2">
              <div class="row">
                <div class="col-4">
                  <label>Competencias aprendidas:</label><br />
                </div>
                <div class="col-4">
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value="Morfología de un componente"
                      v-model="usuario.competencias"
                    />
                    <label class="form-check-label"
                      >Morfología de un componente</label
                    >
                  </div>
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value="One-Way y Two-Way data binding"
                      v-model="usuario.competencias"
                    />
                    <label class="form-check-label"
                      >One-Way y Two-Way data binding</label
                    >
                  </div>
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value="El patrón de diseño MVVM"
                      v-model="usuario.competencias"
                    />
                    <label class="form-check-label"
                      >El patrón de diseño MVVM</label
                    >
                  </div>
                </div>
                <div class="col-4">
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value="Directivas"
                      v-model="usuario.competencias"
                    />
                    <label class="form-check-label">Directivas</label>
                  </div>
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      value="Estado"
                      v-model="usuario.competencias"
                    />
                    <label class="form-check-label">Estado</label>
                  </div>
                </div>
              </div>
            </div>

            <div class="form-group row">
              <label class="col-sm-2 col-form-label">Opinión:</label>
              <div class="col-sm-10">
                <textarea
                  class="form-control"
                  v-model="usuario.opinion"
                  cols="30"
                  rows="2"
                  placeholder="Escribe tu opinión aquí"
                ></textarea>
              </div>
            </div>
          </form>
        </div>

        <div id="planilla" class="col-md-6">
          <div class="card">
            <div class="card-body text-center">
              <p class="display-4">{{ usuario.emoji }}</p>
              <h2>{{ usuario.title }}</h2>
              <h4>Y me parece {{ usuario.apreciacion }}</h4>
              <h5>He aprendido:</h5>
              <p>{{ usuario.competencias.join(", ") }}</p>
              <h5>Mi opinión hasta ahora del framework es:</h5>
              <p>{{ usuario.opinion }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
</template>
