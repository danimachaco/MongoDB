# 🍃 MongoDB — Ejemplos y Scripts Básicos

Colección de scripts para aprender y practicar operaciones esenciales con MongoDB: conexión, creación de colecciones, inserción de documentos y consultas.

---

## 📋 Requisitos

- [MongoDB](https://www.mongodb.com/try/download/community) instalado localmente
- [Node.js](https://nodejs.org/) (para ejecutar los scripts en JavaScript)
- *(Opcional)* [MongoDB Compass](https://www.mongodb.com/products/compass) o `mongosh` como cliente visual

---

## 📁 Estructura del repositorio

```
/
├── ejs_1_MongoDB.mongodb   # Conexión a la base de datos
├── ejs_2_MongoDB.mongodb   # Inserción y consulta de documentos
├── ejs_3_MongoDB.mongodb   # Actualización y eliminación
└── README.md
```

---

## 🚀 Operaciones cubiertas

### Conexión
```js
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
```

### Insertar un documento
```js
db.productos.insertOne({ nombre: "Teclado", precio: 25 });
```

### Buscar documentos
```js
db.productos.find({ precio: { $gt: 20 } });
```

### Actualizar un documento
```js
db.productos.updateOne(
  { nombre: "Teclado" },
  { $set: { precio: 30 } }
);
```

### Eliminar un documento
```js
db.productos.deleteOne({ nombre: "Teclado" });
```

---

## 👤 Autor

**danimachaco** — [github.com/danimachaco](https://github.com/danimachaco)