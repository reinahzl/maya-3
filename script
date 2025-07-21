document.addEventListener("DOMContentLoaded", () => {
  const container = document.getElementById("semestres");
  const creditosSpan = document.getElementById("total-creditos");

  let totalCreditos = 0;

  // Materias con todos los semestres, requisitos incluidos
  const materias = [
    {
      semestre: "Primer Semestre",
      materias: [
        { nombre: "Constitucional", creditos: 15 },
        { nombre: "Personas", creditos: 6 },
        { nombre: "Ideas Político Jurídicas", creditos: 8 },
        { nombre: "Sociedad y Derecho", creditos: 7 },
        { nombre: "Historia del Derecho", creditos: 6 },
      ],
    },
    {
      semestre: "Segundo Semestre",
      materias: [
        { nombre: "Taller de Lecto Escritura Universitaria", creditos: 5 },
        { nombre: "Introducción al Fenómeno Jurídico", creditos: 4 },
        { nombre: "Introducción al Derecho Penal", creditos: 6 },
        { nombre: "Bienes", creditos: 6 },
        { nombre: "Derecho Informático 1", creditos: 6, requisitos: ["Constitucional", "Personas"] },
        { nombre: "Ciencia Política", creditos: 7 },
        { nombre: "Sociedad y Derecho - Ciencia Política", creditos: 2 },
        { nombre: "Derechos Humanos", creditos: 10, requisitos: ["Constitucional"] },
      ],
    },
    {
      semestre: "Segundo Año - Primer Semestre",
      materias: [
        { nombre: "Obligaciones y Contratos", creditos: 14, requisitos: ["Bienes", "Constitucional", "Personas", "Historia del Derecho"] },
        { nombre: "Economía, Derecho e Instituciones", creditos: 8 },
        { nombre: "Introducción a la Metodología de la Investigación", creditos: 6 },
        { nombre: "Procesal 1", creditos: 12, requisitos: ["Bienes", "Constitucional", "Personas", "Historia del Derecho", "Derechos Humanos"] },
        { nombre: "Derecho Informático 2", creditos: 4, requisitos: ["Bienes", "Derecho Informático 1"] },
      ],
    },
    {
      semestre: "Segundo Año - Segundo Semestre",
      materias: [
        { nombre: "D. Penal - Parte General", creditos: 7, requisitos: ["Bienes", "Introducción al Derecho Penal", "Derechos Humanos"] },
        { nombre: "Teoría de la Responsabilidad Civil", creditos: 10, requisitos: ["Obligaciones y Contratos"] },
        { nombre: "Derecho Internacional Público", creditos: 12, requisitos: ["Bienes", "Constitucional", "Personas", "Historia del Derecho", "Introducción al Fenómeno Jurídico"] },
        { nombre: "Trabajo y Seguridad Social 1", creditos: 11, requisitos: ["Constitucional", "Obligaciones y Contratos", "Economía, Derecho e Instituciones"] },
      ],
    },
    {
      semestre: "Tercer Año - Primer Semestre",
      materias: [
        { nombre: "Contratos Especiales", creditos: 12, requisitos: ["Teoría de la Responsabilidad Civil", "Obligaciones y Contratos"] },
        { nombre: "D. Penal - Parte Especial", creditos: 10, requisitos: ["D. Penal - Parte General"] },
        { nombre: "Administrativo 1", creditos: 6, requisitos: ["Bienes", "Constitucional", "Personas"] },
        { nombre: "Registral", creditos: 4, requisitos: ["Bienes", "Personas"] },
        { nombre: "Práctica Profesional 1", creditos: 14 },
      ],
    },
    {
      semestre: "Tercer Año - Segundo Semestre",
      materias: [
        { nombre: "Financiero 1", creditos: 6, requisitos: ["Constitucional", "Administrativo 1", "Economía, Derecho e Instituciones", "D. Penal - Parte General"] },
        { nombre: "Procesal 2", creditos: 12, requisitos: ["Constitucional", "Contratos Especiales", "Procesal 1", "D. Penal - Parte General"] },
        { nombre: "Comercial 1", creditos: 14, requisitos: ["Obligaciones y Contratos", "Teoría de la Responsabilidad Civil", "Economía, Derecho e Instituciones"] },
      ],
    },
    {
      semestre: "Cuarto Año - Primer Semestre",
      materias: [
        { nombre: "Minoridad, Adolescencia y Familia", creditos: 6, requisitos: ["Constitucional", "Contratos Especiales", "Procesal 1"] },
        { nombre: "Comercial 2", creditos: 12, requisitos: ["Constitucional", "Contratos Especiales", "Procesal 1", "Comercial 1"] },
        { nombre: "Seminario del Área", creditos: 2 },
        { nombre: "Familia Personal y Patrimonial", creditos: 8, requisitos: ["Constitucional", "Contratos Especiales", "Procesal 1", "Comercial 1"] },
        { nombre: "Derecho Agrario", creditos: 10, requisitos: ["Administrativo 1", "Contratos Especiales"] },
        { nombre: "Administrativo 2", creditos: 0, requisitos: ["Administrativo 1"] },
      ],
    },
    {
      semestre: "Cuarto Año - Segundo Semestre",
      materias: [
        { nombre: "Financiero 2", creditos: 7, requisitos: ["Financiero 1", "Constitucional"] },
        { nombre: "Sucesiones", creditos: 6, requisitos: ["Contratos Especiales", "Procesal 1"] },
      ],
    },
    {
      semestre: "Quinto Año - Primer Semestre",
      materias: [
        { nombre: "Teoría del Derecho", creditos: 8, requisitos: ["Administrativo 1", "Contratos Especiales", "Procesal 1", "Introducción al Fenómeno Jurídico"] },
        { nombre: "Trabajo y Seguridad Social 2", creditos: 11, requisitos: ["Obligaciones y Contratos", "Teoría de la Responsabilidad Civil", "Economía, Derecho e Instituciones", "Trabajo y Seguridad Social 1"] },
        { nombre: "Consultorio Jurídico 1", creditos: 11 },
      ],
    },
    {
      semestre: "Quinto Año - Segundo Semestre",
      materias: [
        { nombre: "Consultorio Jurídico 2", creditos: 11 },
        { nombre: "Financiamiento Empresarial", creditos: 4, requisitos: ["Contratos Especiales", "Comercial 1", "Comercial 2"] },
        { nombre: "Derecho Internacional Privado", creditos: 12, requisitos: ["Obligaciones y Contratos", "Comercial 1", "Comercial 2", "Familia Personal y Patrimonial", "Sucesiones", "Derecho Internacional Público", "Procesal 1", "Procesal 2"] },
        { nombre: "Situaciones Jurídicas Subjetivas", creditos: 12, requisitos: ["Administrativo 1", "Administrativo 2"] },
      ],
    },
  ];

  // Estado de materias aprobadas
  let aprobadas = new Set();

  // Función para verificar si una materia se puede aprobar según requisitos
  function puedeAprobar(materia) {
    if (!materia.requisitos) return true;
    return materia.requisitos.every(req => aprobadas.has(req));
  }

  // Actualiza visualmente el estado de las materias y calcula créditos
  function actualizarEstado() {
    totalCreditos = 0;

    document.querySelectorAll(".materia").forEach(div => {
      const nombre = div.dataset.nombre;
      const materiaObj = materias.flatMap(s => s.materias).find(m => m.nombre === nombre);

      if (aprobadas.has(nombre)) {
        div.classList.add("aprobada");
        div.classList.remove("bloqueada");
        totalCreditos += materiaObj.creditos;
      } else {
        if (puedeAprobar(materiaObj)) {
          div.classList.remove("bloqueada");
        } else {
          div.classList.add("bloqueada");
        }
        div.classList.remove("aprobada");
      }
    });

    creditosSpan.textContent = totalCreditos;
  }

  // Construir la malla curricular en HTML
  materias.forEach(semestreObj => {
    const semDiv = document.createElement("div");
    semDiv.className = "semestre";

    const title = document.createElement("h2");
    title.textContent = semestreObj.semestre;
    semDiv.appendChild(title);

    semestreObj.materias.forEach(materia => {
      const matDiv = document.createElement("div");
      matDiv.className = "materia bloqueada";
      matDiv.dataset.nombre = materia.nombre;
      matDiv.textContent = `${materia.nombre} (${materia.creditos} cr.)`;

      matDiv.addEventListener("click", () => {
        if (!aprobadas.has(materia.nombre)) {
          if (!puedeAprobar(materia)) {
            alert("No puedes aprobar esta materia aún, te faltan prerrequisitos.");
            return;
          }
          aprobadas.add(materia.nombre);
        } else {
          aprobadas.delete(materia.nombre);
        }
        actualizarEstado();
      });

      semDiv.appendChild(matDiv);
    });

    container.appendChild(semDiv);
  });

  // Mostrar estado inicial
  actualizarEstado();
});
