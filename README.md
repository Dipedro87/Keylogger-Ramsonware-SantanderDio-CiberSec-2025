# Keylogger-Ramsonware-SantanderDio-CiberSec-2025
Simulando um Malware de Captura de Dados Simples em Python e Aprendendo a se Proteger

Ransomware & Keylogger em Python
Este repositório contém a implementação de simulações de malwares (Ransomware e Keylogger) desenvolvidos em Python. O projeto foi realizado como parte do desafio do Bootcamp de Cibersegurança, com o objetivo de compreender o funcionamento ofensivo para fortalecer estratégias defensivas.

⚠️ AVISO LEGAL: Este projeto foi desenvolvido estritamente para fins educacionais e acadêmicos em ambiente controlado. O uso desses scripts para atacar sistemas sem consentimento prévio é ilegal e antiético.

🛠️ Ferramentas e Bibliotecas Utilizadas
Python 3
Cryptography (Fernet): Para implementação da criptografia simétrica.
Pynput: Para captura de eventos do teclado.
OS / IO: Para manipulação de arquivos e sistema operacional.
📂 Estrutura do Projeto
1. Ransomware (Criptografia de Arquivos)
O conjunto de scripts simula um ataque onde arquivos são sequestrados e só podem ser recuperados com uma chave específica.

ransomware.py:
Gera uma chave de criptografia simétrica (chave.key).
Percorre o diretório atual procurando arquivos.
Lógica de Proteção: Possui uma lista de exceções (Allowlist) para não criptografar o próprio script, a chave ou a nota de resgate.
Criptografa os arquivos encontrados sobrescrevendo os dados originais.
Gera um arquivo LEIA ISSO.txt com o pedido de resgate.
descriptografar.py:
Lê a chave gerada (chave.key).
Percorre os arquivos criptografados.
Reverte o processo, devolvendo o conteúdo original dos arquivos.
2. Keylogger (Captura de Teclas)
O script monitora a entrada do teclado do usuário e registra o conteúdo em um arquivo de log local.

keylogger.py:
Utiliza a biblioteca pynput para escutar eventos de press (pressionar tecla).
Tratamento de Dados: Formata teclas especiais (Space, Enter, Tab) para manter o texto legível e ignora teclas de controle (Shift, Ctrl, Alt) para evitar poluição visual.
Salva tudo em tempo real no arquivo log.txt.
keylogger_em.py:
Exfiltração via E-mail: Estende a funcionalidade básica integrando a biblioteca smtplib para envio de dados via protocolo SMTP.
Ciclos de Reporte: Configurado para acumular as teclas e enviar o log por e-mail em intervalos regulares (ex: a cada 60 segundos), simulando o roubo ativo de credenciais.
🚀 Passo a passo
Pré-requisitos
Instale as bibliotecas necessárias:

pip install cryptography pynput
Simulando o Ransomware:
Crie uma pasta de teste e coloque alguns arquivos de texto (.txt) dentro.

image
Execute o malware: python ransomware.py.

py
Resultado: Os arquivos ficarão ilegíveis e o arquivo chave.key será criado juntamente com o arquivo LEIA ISSO.txt.

Recuperação de arquivos
Execute o decifrador: python descriptografar.py.

Resultado: Os arquivos voltam ao texto original.

Simulando o Keylogger
Instale a biblioteca:

pip install pynput
Execute o script: python keylogger.py.

Digite qualquer texto em outra janela (bloco de notas, navegador).


Verifique o arquivo log.txt criado na pasta. O conteúdo digitado estará lá.

Keylogger com envio de dados para o e-mail
! Antes de tudo crie um e-mail para testes e ative a configuração em 2 etapas.

Acesse o site:

account.google.com/apppasswords
E crie uma senha para utilizar durante o teste:


Execute o código e digite algo no computador para teste.




