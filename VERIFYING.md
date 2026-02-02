# Verificarea funcționării aplicației

Acest document descrie pașii recomandați pentru a valida rapid funcționarea aplicației și pentru a rula verificările interne ale proiectului.

## 1) Verificare rapidă (selftest, mod quick)

Rulați selftest-ul în mod „quick” pentru a valida structura proiectului și verificările de bază:

```bash
python -m app.selftest --mode quick --config config.json
```

Acest test verifică mediul Python, structura proiectului și câteva verificări de securitate. Dacă vedeți avertizări despre dependențe lipsă, instalați pachetele din `requirements.txt` și rulați din nou.

## 2) Verificare completă (selftest, mod full)

Pentru o verificare mai amplă:

```bash
python -m app.selftest --mode full --config config.json
```

## 3) Instalarea dependențelor

Înainte de rulare, este recomandat:

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
```

## 4) Rezultatul rulării în acest mediu (sandbox)

În sandbox am rulat selftest-ul în mod `quick` și rezultatul a fost **SUCCESS**, cu avertizare pentru dependențe lipsă:

- **Missing deps**: `ccxt`, `pandas`, `numpy`, `fastapi`, `uvicorn`, `requests`, `tqdm`.

După instalarea dependențelor, rulați din nou pentru a elimina avertizarea.
