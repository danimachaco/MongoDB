📦 Proyecto MongoDB
Este repositorio contiene ejemplos y scripts básicos para trabajar con MongoDB, incluyendo conexión, creación de colecciones, inserción de documentos y consultas simples.

🚀 Requisitos
MongoDB instalado en tu máquina

Node.js (si usas scripts en JavaScript)

Cliente MongoDB opcional: MongoDB Compass o mongosh

🔌 Conexión a la base de datos
js
const { MongoClient } = require("mongodb");

const uri = "mongodb://localhost:27017";
const client = new MongoClient(uri);

async function run() {
  try {
    await client.connect();
    console.log("Conectado a MongoDB");
  } finally {
    await client.close();
  }
}

run();
📁 Estructura del repositorio
Código
/src
  ├── conexion.js
  ├── insertar.js
  ├── buscar.js
  └── actualizar.js
README.md
🛠️ Operaciones básicas
➕ Insertar documentos
js
db.productos.insertOne({ nombre: "Teclado", precio: 25 });
🔍 Buscar documentos
js
db.productos.find({ precio: { $gt: 20 } });
✏️ Actualizar documentos
js
db.productos.updateOne(
  { nombre: "Teclado" },
  { $set: { precio: 30 } }
);
❌ Eliminar documentos
js
db.productos.deleteOne({ nombre: "Teclado" });