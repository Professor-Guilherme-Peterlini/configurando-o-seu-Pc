# Guia de Instalação: Ubuntu e Windows no VirtualBox

## Preparação Inicial

### Downloads Necessários:
1. ISO do Ubuntu: https://ubuntu.com/download/desktop
2. ISO do Windows: https://www.microsoft.com/software-download/windows10
3. VirtualBox: https://www.virtualbox.org/wiki/Downloads

## Parte 1: Instalando Ubuntu no VirtualBox

### 1. Criar Nova Máquina Virtual
1. Abra o VirtualBox
2. Clique em "Novo"
3. Configure:
   - Nome: Ubuntu
   - Pasta da Máquina: [mantenha o padrão]
   - Tipo: Linux
   - Versão: Ubuntu (64-bit)
   - Clique em "Próximo"

### 2. Configurar Hardware
1. Memória (RAM):
   - Aloque 4096 MB (4GB)
   - Clique em "Próximo"

2. Disco Rígido:
   - Selecione "Criar um disco rígido virtual agora"
   - Tipo: VDI (VirtualBox Disk Image)
   - Alocação: Dinamicamente alocado
   - Tamanho: 25GB
   - Clique em "Criar"

### 3. Configurações Adicionais
1. Selecione a VM criada
2. Clique em "Configurações"
3. Sistema:
   - Processador: 2 CPUs
   - Habilitar PAE/NX
4. Display:
   - Memória de Vídeo: 128MB
   - Habilitar Aceleração 3D
5. Armazenamento:
   - Controladora IDE: Clique no ícone de CD
   - Escolha o arquivo ISO do Ubuntu
6. Rede:
   - Adaptador 1: NAT

### 4. Instalação do Ubuntu
1. Inicie a VM
2. Selecione "Try or Install Ubuntu"
3. Escolha o idioma: Português
4. Selecione "Instalar Ubuntu"
5. Layout do teclado: Portuguese (Brazil)
6. Escolha:
   - Instalação normal
   - Baixar atualizações durante a instalação
7. Tipo de instalação:
   - "Apagar disco e instalar Ubuntu"
   - Clique em "Instalar agora"
8. Confirme as mudanças no disco
9. Escolha seu fuso horário
10. Configure sua conta:
    - Nome
    - Nome do computador
    - Nome de usuário
    - Senha
11. Aguarde a instalação completar
12. Reinicie quando solicitado

### 5. Pós-Instalação
1. Instale Guest Additions:
   - Dispositivos > Inserir imagem do CD dos Adicionais para Convidado
   - Abra o terminal
   ```bash
   cd /media/[seu-usuario]/VBox_GAs_[versão]
   sudo ./VBoxLinuxAdditions.run
   ```
2. Atualize o sistema:
   ```bash
   sudo apt update
   sudo apt upgrade -y
   ```

## Parte 2: Instalando Windows no VirtualBox

### 1. Criar Nova Máquina Virtual
1. Clique em "Novo"
2. Configure:
   - Nome: Windows
   - Tipo: Microsoft Windows
   - Versão: Windows 10 (64-bit)
   - Clique em "Próximo"

### 2. Configurar Hardware
1. Memória (RAM):
   - Aloque 4096 MB (4GB)
   - Clique em "Próximo"

2. Disco Rígido:
   - Criar um disco rígido virtual agora
   - Tipo: VDI
   - Alocação: Dinamicamente alocado
   - Tamanho: 50GB
   - Clique em "Criar"

### 3. Configurações Adicionais
1. Sistema:
   - Processador: 2 CPUs
   - Habilitar PAE/NX
   - Ordem de Boot: Óptica, Disco
2. Display:
   - Memória de Vídeo: 128MB
   - Habilitar Aceleração 3D
3. Armazenamento:
   - Controladora IDE: Selecione o ISO do Windows
4. Rede:
   - Adaptador 1: NAT

### 4. Instalação do Windows
1. Inicie a VM
2. Pressione qualquer tecla para iniciar pelo DVD
3. Configuração inicial:
   - Idioma: Português (Brasil)
   - Formato de hora e moeda: Português (Brasil)
   - Teclado: Português (Brasil ABNT2)
4. Clique em "Instalar agora"
5. Chave do produto:
   - Selecione "Não tenho a chave do produto" (para teste)
6. Selecione a versão:
   - Windows 10 Pro
7. Aceite os termos de licença
8. Tipo de instalação:
   - Personalizada: Instalar somente o Windows
9. Particionamento:
   - Selecione o espaço não alocado
   - Clique em "Novo" e depois "Aplicar"
10. Aguarde a instalação

### 5. Configuração Inicial do Windows
1. Região: Brasil
2. Layout do teclado: Português (Brasil ABNT2)
3. Pule a adição de segundo layout
4. Configure a rede:
   - Selecione "Configurar para rede doméstica"
5. Configure a conta:
   - Nome de usuário
   - Senha (opcional)
6. Configure as opções de privacidade:
   - Desative o que não quiser usar

### 6. Pós-Instalação
1. Instale o Guest Additions:
   - Dispositivos > Inserir imagem do CD dos Adicionais para Convidado
   - Execute VBoxWindowsAdditions
   - Reinicie quando solicitado
2. Windows Update:
   - Configurações > Windows Update
   - Verificar atualizações
   - Instale todas as atualizações disponíveis

## Dicas Importantes

### Para Ubuntu:
1. Use a versão LTS para maior estabilidade
2. Mantenha o sistema atualizado
3. Configure o compartilhamento de área de transferência

### Para Windows:
1. Instale os drivers após a instalação
2. Ative o Windows se necessário
3. Instale um antivírus

### Geral:
1. Crie snapshots após a instalação limpa
2. Configure pastas compartilhadas se necessário
3. Ajuste a memória RAM conforme necessidade
4. Mantenha os Guest Additions atualizados

## Resolução de Problemas

### Problemas Comuns no Ubuntu:
1. Tela preta após boot:
   - Desligue a VM
   - Configurações > Sistema > Habilite PAE/NX
2. Resolução baixa:
   - Reinstale Guest Additions

### Problemas Comuns no Windows:
1. Erro "VT-x is not available":
   - Habilite a virtualização na BIOS
2. Tela azul:
   - Verifique compatibilidade de hardware
   - Reinstale Guest Additions