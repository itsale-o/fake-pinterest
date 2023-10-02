# Arquivo de Anotações 

## init


`app = Flask(__name__)`: estamos criando um aplicativo dizendo que se trata de um app do Flask
`app.config["SQLALCHEMY_DATABASE_URI"] = "sqlite:///comunidade.db"`: será criada uma pasta dentro do
projeto que conterá um banco de dados sqlite
`database = SQLAlchemy(app)`: cria o banco de dados de fato

## models.py

Quando colocamos `primary_key=True` na criação do id do suário, estamos falando para o banco de dados que aquilo
se trata de uma chave priária, o que significa que sempre que um usuário novo for criado, não precisamos 
dizer para o banco de dados qual é o id daquele usuário, ele será automaticamente criado

A imagem é uma string, pois na realidade não estamos passando a imagem em si, mas o local onde a imagem está
armazenada

`fotos = database.Relationship()`: não será criada uma tabela no banco de dados, apenas uma relação. Apenas um
link que relaciona a tabela de usuários com a tabela de fotos

`lazy=True`: permite uma busca mais eficiente no banco de dados quando é criado um `database.Relationship()`.

O `ForeignKey("tabela.coluna")` é o que recebe o `Relationship()`.