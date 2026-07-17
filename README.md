# Simulador PAES · Medicina

App estática. Sliders NEM / Ranking / M1 / Comp. Lectora / Ciencias (escala 100–1000), puntaje ponderado en vivo, selector de universidad.

## Deploy en GitHub Pages jeje
```bash
git init && git add . && git commit -m "simulador PAES medicina"
git branch -M main
git remote add origin git@github.com:<user>/<repo>.git
git push -u origin main
```
Luego: Settings → Pages → Source: `main` / root.

## Prueba local
```bash
python3 -m http.server 8000
```
Abrir `http://localhost:8000` (con `file://` el fetch del JSON falla).

## Editar universidades
Todo en `universidades.json`:
```json
{
  "nombre": "U. Nueva",
  "ponderaciones": { "nem": 10, "ranking": 20, "lenguaje": 10, "m1": 30, "ciencias": 30 }
}
```
- Deben sumar 100 (la app muestra advertencia si no).
- Valores incluidos son **referenciales**: verificar contra la oferta oficial DEMRE de cada proceso.

## Agregar un factor (p. ej. M2)
1. Agregar `"m2": X` en cada universidad del JSON.
2. En `index.html`, agregar `{ key: "m2", label: "Matemática 2 (M2)" }` al array `FACTORES`.