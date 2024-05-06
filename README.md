# Construindo aplicações com NodeJS & TypeScript

## Acervo

**Download & Install**

[`Alura`](https://www.alura.com.br/artigos/como-instalar-node-js-windows-linux-macos) |
[`Node`](https://nodejs.org/en/download/) |
[`Node Version Manager`](https://github.com/nvm-sh/nvm)

**Documentações**

[`NodeJS`](https://nodejs.org/docs/latest/api/) | [`TypeScript`](https://www.typescriptlang.org/docs/) |
[`Express`](https://expressjs.com/en/starter/installing.html) | [`ts-node-dev`](https://www.npmjs.com/package/ts-node-dev) |
[`dotenv`](https://www.dotenv.org/docs#getting-started) | [`uuid`](https://www.npmjs.com/package/uuid)

## Instalação no Windows

`Para fazer a instalação no windows, basta realizar o download do instalador LTS no site oficial do Node e realizar o passo a passo de instalação.`

## Instalação no Linux (Ubuntu)

`Para instalar a versão LTS no Linux Ubuntu, devemos digitar no terminal os comandos abaixo.`

~~~
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
~~~

~~~
sudo apt-get install -y nodejs
~~~

## Checagem rápida

`Rode os comandos abaixo.`

~~~
node -v
~~~

~~~
npm -v
~~~

## Inicialização do repositório git

~~~
git init
~~~

> Realize as configurações necessárias no seu repositório (.gitignore, licença e etc).

## Inicialização do nosso projeto Node

~~~
npm init -y
~~~

## Instalando as dependências do projeto

**Commands Examples**

```markdown
npm install <package-name>
npm uninstall <package-name>

npm i <package-name>
npm i <package-name> -D
npm i <package-name> --save-dev
```

**Dependências necessárias para o projeto**

- typescript `Development Dependencies`
- ts-node-dev `Development Dependencies`
- express `Dependencies`
- dotenv `Dependencies`
- uuid `Dependencies`

~~~
npm i typescript ts-node-dev @types/express -D
~~~

~~~
npm i express dotenv uuid
~~~

## Configurando os scripts no package.json

```json
{
  "scripts": {
    "start:dev": "ts-node-dev --inspect --ignore-watch node_module src/shared/core/app.ts",
    "start": "node dist/index.js",
    "build": "tsc"
  }
}
```

## Configurações de Build

Podemos começar gerando um arquivo `tsconfig.json`, usando o comando:

~~~
tsc --init
~~~

Exemplo de `tsconfig.json` com algumas configurações.

```json
{
  "compilerOptions": {
    "target": "ES2016",
    "module": "CommonJS",
    "rootDir": "src",
    "outDir": "./dist",
    "moduleResolution": "Node",
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "skipLibCheck": true,
  }
}
```
Vamos analisar cada uma das configurações presentes no arquivo `tsconfig.json` que você forneceu:

1. `"target": "ES2016"`:
   - Isso define para qual versão do ECMAScript o TypeScript deve compilar o código. No caso, o código será compilado para ES6 (ECMAScript 2015).

2. `"module": "CommonJS"`:
   - Define o sistema de módulos a ser usado. Aqui, está configurado para CommonJS, que é comumente usado no ambiente Node.js. Isso permite o uso de `require` para importar módulos.

3. `"rootDir": "src"`:
   - Especifica o diretório onde estão localizados os arquivos principais do sistema. Isso é útil quando se trabalha com múltiplos diretórios e se deseja que o TypeScript compile apenas os arquivos dentro de um diretório específico.

4. `"outDir": "./dist"`:
   - Define o diretório de saída para os arquivos JavaScript compilados. Neste caso, os arquivos JavaScript serão colocados no diretório `dist` na raiz do projeto.

5. `"moduleResolution": "Node"`:
   - Especifica como o TypeScript procura um arquivo de um determinado especificador de módulo. Aqui, está configurado para o modo de resolução Node.js, que segue as regras de resolução de módulos do Node.js.

6. `"forceConsistentCasingInFileNames": true`:
   - Força consistência nos nomes de arquivo. Isso significa que os nomes de arquivos devem corresponder exatamente à forma como são referenciados nos imports, incluindo a capitalização.

7. `"strict": true`:
   - Habilita todas as opções de compilação rigorosas. Isso inclui opções como `noImplicitAny`, `strictNullChecks`, `strictFunctionTypes`, entre outras, para garantir um código mais seguro e robusto.

8. `"skipLibCheck": true`:
   - Pula a verificação de arquivos de biblioteca (como arquivos de definição de tipo `.d.ts`). Isso pode acelerar o processo de compilação, mas pode levar a erros de tipo em bibliotecas externas.

Essas configurações ajudam a definir o comportamento do compilador TypeScript e a estrutura do projeto.

## CheckList

- [x] Node instalado.
- [x] Repositório git inicializado.
- [x] Projeto Node inicializado.
- [x] Dependências instaladas.
- [x] Configuração dos scripts (package.json) realizadas.
- [x] Configuração do tsconfig.json realizada.

## NPM Commands

```markdown
1. npm init
   - Inicia o processo de criação de um novo projeto npm. Ele solicita informações sobre o projeto e gera um arquivo `package.json`.

2. npm install
   - Instala todas as dependências listadas no arquivo `package.json` do projeto.

3. npm install <package-name>
   - Instala um pacote específico do npm localmente no projeto.

4. npm install -g <package-name>
   - Instala um pacote globalmente no sistema, tornando-o acessível em qualquer lugar do terminal.

5. npm install --save <package-name>
   - Instala um pacote e adiciona-o automaticamente como uma dependência no arquivo `package.json`.

6. npm install --save-dev <package-name>
   - Instala um pacote e adiciona-o automaticamente como uma dependência de desenvolvimento no arquivo `package.json`.

7. npm uninstall <package-name>
   - Remove um pacote específico do projeto.

8. npm uninstall -g <package-name>
   - Remove um pacote globalmente do sistema.

9. npm update
   - Atualiza todas as dependências listadas no arquivo `package.json` para as versões mais recentes permitidas.

10. npm update <package-name>
    - Atualiza um pacote específico para a versão mais recente permitida.

11. npm outdated
    - Lista as dependências que estão desatualizadas em relação às versões mais recentes disponíveis.

12. npm run <script-name>
    - Executa um script especificado no campo "scripts" do arquivo `package.json`.

13. npm test
    - Executa os testes definidos no campo "scripts" com a chave "test" no arquivo `package.json`.

14. npm publish
    - Publica o pacote no registro npm, tornando-o disponível para ser instalado por outros usuários.

15. npm search <search-term>
    - Pesquisa pacotes no registro npm com base no termo de pesquisa fornecido.

16. npm info <package-name>
    - Exibe informações detalhadas sobre um pacote específico do npm.

17. npm config set <key> <value>
    - Define uma configuração específica do npm.

18. npm config get <key>
    - Obtém o valor de uma configuração específica do npm.

19. npm cache clean
    - Limpa o cache do npm, removendo todos os pacotes armazenados em cache.

20. npm doctor
    - Executa um diagnóstico no ambiente npm para identificar e corrigir problemas comuns.
```
