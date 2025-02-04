# robotframework-windows
Tutorial: Configurando um Ambiente Virtual e Instalando o Robot Framework no Windows

# Instalação do Robot Framework Wundows

Passo 1: Instalar o Python

    Baixe o Python:
        Acesse o site oficial: python.org.
        Baixe a versão mais recente do Python 3.x (recomendado 3.7 ou superior).
    Instale o Python:
        Durante a instalação:
            Marque a opção "Add Python to PATH".
            Prossiga com a instalação padrão ou personalizada.

Passo 2: Criar um Ambiente Virtual

    Abra o Prompt de Comando:
        Use Win + R, digite cmd e pressione Enter.

    Escolha ou crie um diretório para o projeto:

mkdir robot_project
cd robot_project

Crie o ambiente virtual:

    Execute o comando:

    python -m venv venv

    Isso criará uma pasta chamada venv no diretório do projeto.

Ative o ambiente virtual:

    Execute o comando:

        venv\Scripts\activate

        O nome do ambiente virtual (venv) aparecerá no início da linha do terminal, indicando que está ativo.

Passo 3: Instalar o Robot Framework

    Certifique-se de que o ambiente virtual está ativo:
        Você deve ver algo como (venv) no terminal.

    Instale o Robot Framework:

pip install robotframework

Verifique se a instalação foi bem-sucedida:

    robot --version

        Isso exibirá a versão do Robot Framework instalada.

Passo 4: Instalar o SeleniumLibrary

    Instale a biblioteca SeleniumLibrary:

pip install robotframework-seleniumlibrary

Instale o Selenium WebDriver:

    O Selenium precisa de drivers específicos para controlar os navegadores (Chrome, Firefox, etc.). Aqui está como configurar para o Chrome:
        Baixe o ChromeDriver compatível com a versão do seu navegador:
            Acesse: ChromeDriver Downloads.
        Extraia o arquivo baixado e mova o executável para um local acessível (como C:\webdriver).
        Adicione o caminho ao sistema:
            Clique com o botão direito no ícone Este Computador > Propriedades.
            Vá em Configurações Avançadas do Sistema > Variáveis de Ambiente.
            Edite a variável Path e adicione o caminho onde o ChromeDriver foi salvo.

Verifique a instalação do Selenium:

    Execute este comando para testar:

        python -m selenium.webdriver.chrome.service

Passo 5: Criar um Arquivo de Teste

    No diretório do projeto, crie um arquivo .robot:

notepad test_suite.robot

Insira o seguinte código como exemplo:

    *** Settings ***
    Library  SeleniumLibrary

    *** Test Cases ***
    Open Browser and Search
        Open Browser  https://www.google.com  chrome
        Input Text  name:q  Robot Framework
        Press Keys  name:q  RETURN
        Close Browser

Passo 6: Executar o Arquivo de Teste

    Certifique-se de que o ambiente virtual está ativo.
    Execute o teste com o comando:

    robot test_suite.robot

    O resultado será exibido no terminal e nos arquivos log.html e report.html, gerados automaticamente no diretório do projeto.

Dicas Adicionais

    Atualizar o pip (se necessário):

pip install --upgrade pip

Para sair do ambiente virtual:

    deactivate

    Caso use outro navegador (como Firefox ou Edge), baixe o driver correspondente.

Agora você está pronto para usar o Robot Framework com Selenium no Windows! 🚀 Se precisar de ajuda em alguma etapa, é só avisar. 😊
