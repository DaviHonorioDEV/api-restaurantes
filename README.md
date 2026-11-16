# API Restaurantes 🍔

API feita com **FastAPI** que consome dados de restaurantes de uma API externa e permite consultar o cardápio de cada um.

Projeto de estudo desenvolvido durante o curso *Python: avance na Orientação a Objetos e consuma API*, da Alura.

## O que ela faz

- Busca os dados de vários restaurantes numa API pública (JSON)
- Lista todos os restaurantes e itens do cardápio
- Filtra o cardápio de um restaurante específico pelo nome
- Gera documentação interativa automática (Swagger)

O script `app.py` também separa os dados e salva um arquivo `.json` com o cardápio de cada restaurante (os arquivos já estão no repositório).

## Tecnologias

- Python
- FastAPI
- Uvicorn
- Requests

## Endpoints

| Método | Rota | Descrição |
|---|---|---|
| GET | `/api/hello` | Mensagem de boas-vindas |
| GET | `/api/restaurantes/` | Lista todos os restaurantes |
| GET | `/api/restaurantes/?restaurante=KFC` | Cardápio de um restaurante |

Restaurantes disponíveis: `McDonald’s`, `Burger King`, `KFC`, `Taco Bell`, `Pizza Hut` e `Wendy’s`.

> O nome precisa ser escrito exatamente igual, com maiúsculas e o apóstrofo `’` em McDonald’s e Wendy’s. Se o nome não existir, a API devolve o cardápio vazio.

Exemplo de resposta de `/api/restaurantes/?restaurante=KFC`:

```json
{
  "Restaurante": "KFC",
  "Cardapio": [
    { "nome": "...", "price": "...", "description": "..." }
  ]
}
```

## Como rodar

```bash
# 1. Clonar o repositório
git clone https://github.com/DaviHonorioDEV/api-restaurantes.git
cd api-restaurantes

# 2. Criar e ativar o ambiente virtual
python3 -m venv venv
source venv/bin/activate        # no Windows: venv\Scripts\activate

# 3. Instalar as dependências
pip install -r requirements.txt

# 4. Rodar a API
uvicorn main:app --reload
```

Depois, acesse a documentação em **http://127.0.0.1:8000/docs**.

## O que aprendi

- Consumir uma API externa com `requests`
- Criar endpoints com FastAPI e usar parâmetros de consulta (*query parameters*)
- Manipular e salvar dados em JSON
- Usar ambiente virtual e `requirements.txt`
