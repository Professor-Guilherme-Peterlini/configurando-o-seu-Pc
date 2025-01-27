# Configuração de Ambiente de Desenvolvimento Web
## Windows e Linux (Ubuntu)

## Parte 1: Configuração Python

### Windows:
1. Download e Instalação:
   - Acesse https://www.python.org/downloads/
   - Baixe a última versão estável
   - Execute o instalador
   - ✅ Marque "Add Python to PATH"
   - Escolha "Customize installation"
   - ✅ Selecione todas as opções
   - Clique em "Install"

2. Verificar instalação:
```cmd
python --version
pip --version
```

3. Configurar ambiente virtual:
```cmd
# Instalar virtualenv
pip install virtualenv

# Criar pasta de projetos
mkdir projetos-web
cd projetos-web

# Criar ambiente virtual
python -m venv venv

# Ativar ambiente
venv\Scripts\activate
```

### Ubuntu:
1. Instalação:
```bash
# Atualizar sistema
sudo apt update
sudo apt upgrade -y

# Instalar Python e pip
sudo apt install python3 python3-pip python3-venv -y

# Verificar instalação
python3 --version
pip3 --version
```

2. Configurar ambiente virtual:
```bash
# Criar pasta de projetos
mkdir ~/projetos-web
cd ~/projetos-web

# Criar ambiente virtual
python3 -m venv venv

# Ativar ambiente
source venv/bin/activate
```

### Configurações Comuns Python (Ambos os sistemas):
1. Instalar pacotes essenciais:
```bash
pip install flask django requests beautifulsoup4 pandas numpy
```

2. Configurar VS Code para Python:
   - Instalar extensão "Python" da Microsoft
   - Instalar extensão "Pylance"
   - Instalar extensão "Python Test Explorer"

## Parte 2: Configuração JavaScript (Node.js)

### Windows:
1. Instalação Node.js:
   - Acesse https://nodejs.org/
   - Baixe a versão LTS
   - Execute o instalador
   - Siga as opções padrão

2. Verificar instalação:
```cmd
node --version
npm --version
```

### Ubuntu:
1. Instalação via NVM:
```bash
# Instalar NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

# Recarregar configurações
source ~/.bashrc

# Instalar Node.js LTS
nvm install --lts

# Verificar instalação
node --version
npm --version
```

### Configurações Comuns JavaScript (Ambos os sistemas):
1. Configurar NPM:
```bash
# Criar arquivo package.json
npm init -y

# Instalar pacotes globais úteis
npm install -g nodemon eslint prettier
```

2. Configurar ESLint:
```bash
# Inicializar ESLint
npx eslint --init

# Escolher:
# - To check syntax, find problems, and enforce code style
# - JavaScript modules (import/export)
# - None of these (para projetos front-end)
# - No TypeScript
# - Browser
# - Use popular style guide
# - Airbnb
# - JavaScript
# - Yes (install dependencies)
```

3. Criar arquivo .prettierrc:
```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 80,
  "tabWidth": 2
}
```

## Parte 3: Configuração HTML/CSS

### Configurações Comuns (Windows e Ubuntu):

1. Extensões VS Code:
   - Live Server
   - HTML CSS Support
   - IntelliSense for CSS
   - HTML Snippets
   - CSS Peek
   - Auto Rename Tag
   - Color Highlight

2. Criar estrutura de projeto básica:
```bash
mkdir meu-projeto
cd meu-projeto
mkdir css js img
touch index.html css/style.css js/script.js
```

3. Template HTML básico:
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Projeto</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <h1>Meu Projeto Web</h1>
    <script src="js/script.js"></script>
</body>
</html>
```

4. Configurar CSS Reset (style.css):
```css
/* Reset básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
}
```

## Parte 4: Frameworks e Ferramentas Adicionais

### Instalação de Frameworks Comuns:

1. React:
```bash
# Criar novo projeto React
npx create-react-app meu-projeto-react
cd meu-projeto-react
npm start
```

2. Vue.js:
```bash
# Instalar Vue CLI
npm install -g @vue/cli

# Criar projeto Vue
vue create meu-projeto-vue
```

3. Bootstrap:
```bash
# Via NPM
npm install bootstrap

# Via CDN (adicionar ao HTML)
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
```

4. Tailwind CSS:
```bash
# Instalar Tailwind
npm install -D tailwindcss
npx tailwindcss init
```

## Parte 5: Configuração do Git

### Windows e Ubuntu:
1. Instalação Git:
   - Windows: Baixe do https://git-scm.com/
   - Ubuntu: `sudo apt install git`

2. Configuração inicial:
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```

3. Criar .gitignore:
```
# Node
node_modules/
npm-debug.log

# Python
venv/
__pycache__/
*.pyc

# VS Code
.vscode/

# Ambiente
.env
```

## Parte 6: Configurações do VS Code

1. settings.json:
```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.tabSize": 2,
  "editor.wordWrap": "on",
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
  "files.autoSave": "onFocusChange",
  "liveServer.settings.donotShowInfoMsg": true
}
```

2. Extensões recomendadas adicionais:
   - GitLens
   - Docker
   - REST Client
   - Code Spell Checker
   - Path Intellisense

## Parte 7: Dicas e Boas Práticas

1. Organização de Projetos:
```
projeto/
├── src/
│   ├── assets/
│   ├── components/
│   ├── styles/
│   └── utils/
├── public/
├── tests/
└── docs/
```

2. Comandos úteis:
```bash
# Servidor Python
python -m http.server 8000

# Servidor Node
npx serve

# Verificar portas em uso
# Windows
netstat -ano | findstr :PORT
# Linux
sudo lsof -i :PORT
```

3. Checklist de Desenvolvimento:
- [ ] Ambiente virtual ativo (Python)
- [ ] Dependencies atualizadas
- [ ] ESLint configurado
- [ ] Prettier configurado
- [ ] Git inicializado
- [ ] .gitignore configurado
- [ ] README.md criado

## Parte 8: Resolução de Problemas

### Problemas Comuns:

1. Node.js:
- Erro "node_modules not found":
```bash
rm -rf node_modules package-lock.json
npm install
```

2. Python:
- Erro de módulo não encontrado:
```bash
pip install -r requirements.txt
```

3. Git:
- Erro de merge:
```bash
git stash
git pull
git stash pop
```

4. VS Code:
- Live Server não funciona:
  - Verifique se o arquivo está salvo
  - Verifique se está na pasta correta
  - Reinstale a extensão

### Manutenção:

1. Atualizações regulares:
```bash
# Node.js
npm update

# Python
pip list --outdated
pip install --upgrade [pacote]

# Sistema (Ubuntu)
sudo apt update && sudo apt upgrade
```

2. Limpeza:
```bash
# Node.js
npm cache clean --force

# Python
pip cache purge

# Git
git gc
```