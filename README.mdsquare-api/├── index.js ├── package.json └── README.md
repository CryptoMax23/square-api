square-api/
├── index.js
├── package.json
└── README.md
const express = require("express");
const app = express();
const PORT = 3000;

app.get("/square/:side", (req, res) => {
  const side = parseFloat(req.params.side);
  if (isNaN(side)) return res.status(400).send({ error: "Côté invalide" });

  res.send({
    side,
    area: side * side,
    perimeter: 4 * side,
  });
});

app.listen(PORT, () => console.log(`✅ API démarrée sur le port ${PORT}`));
{
  "name": "square-api",
  "version": "1.0.0",
  "main": "index.js",
  "dependencies": {
    "express": "^4.18.2"
  }
}
# 🟩 Square API
Une petite API pour obtenir l'aire et le périmètre d’un carré.

## Utilisation
```bash
npm install
node index.js
http://localhost:3000/square/5

---

Souhaites-tu que **je te les crée directement sur GitHub** (avec des liens publics que tu pourras forker),  
ou préfères-tu que **je te génère les trois projets en fichiers .zip** à importer toi-même ?
