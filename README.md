# Order Tracking

API de rastreamento de encomendas em Django. Cada encomenda tem remetente e destinatário (pessoa física ou jurídica), cidades de origem e destino, peso, volume, um código de rastreio e um histórico de passagem por cidades.

## Rotas (`/api/`)

| Rota | Recurso |
| --- | --- |
| `packages`, `packages/<id>` | Encomendas |
| `packages/<código>/log` | Histórico de rastreio de uma encomenda |
| `person`, `person/<id>` | Pessoas |
| `natural-person`, `natural-person/<id>` | Pessoas físicas (CPF) |
| `legal-person`, `legal-person/<id>` | Pessoas jurídicas (CNPJ, nome fantasia) |
| `states`, `states/<id>` | Estados |
| `cities`, `cities/<id>` | Cidades |

As views são escritas em Django puro, sem DRF, com helpers próprios de serialização em `helpers/`. Exemplos de requisição para cada recurso estão em `tests/*.http` (extensão REST Client do VS Code).

## Stack

Python · Django · SQLite

## Como rodar

```bash
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```
