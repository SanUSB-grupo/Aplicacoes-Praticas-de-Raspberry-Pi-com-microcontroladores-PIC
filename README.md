# Aplicações Práticas de Raspberry Pi com microcontroladores PIC

Aprenda de forma simples a gravação online de microcontroladores via Raspberry Pi

![PicRPI](assets/picrpi.jpeg)

![sanusbbb](assets/sanusbbb.jpeg)

Grupo SanUSB

_Dedicamos este trabalho_

_a Deus, às nossas famílias, a todos_

_os IFCEanos, amigos, alunos e integrantes_

_do grupo SanUSB._

**Sumário**

1.INTRODUÇÃO 7

2.S.O. no Raspberry Pi 10

2.1 Raspbian 10

3.Instalação 11

3.1 Instalação do software 11

3.2 Formatar o SD Card (FAT ou FAT32 padrão) 11

3.3 Instalar o Sistema Operacional no cartão 12

[3.4 Raspberry Pi – Como fazer um backup do seu sistema 13](#641552765388041-_Toc449098141)

[3.5 Criação do arquivo de imagem do sistema 13](#641552765388041-_Toc449098142)

[3.6 Instalação do  arquivo de imagem no cartão 15](#641552765388041-_Toc449098143)

[3.7 Instalação rápida do Raspbian e programas iniciais necessários 16](#641552765388041-_Toc449098144)

4.Minibian (MINImal raspBIAN) 17

[4.1 Acesso Remoto SSH (Secure SHell) por linha de comando 18](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098146)

[4.2 Acesso a um Raspberry remoto por interface gráfica 18](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098147)

[4.3 Instalando o software do servidor TightVNC 18](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098148)

[4.4 Iniciando o servidor e configurando uma senha 19](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098149)

[4.5 Script de instalação automática do tightvnc para inicialização automática 20](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098150)

[4.6 Mudar senha do VNC 21](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098151)

[O VNC só aceita senha com oito caracteres, caso seja digitada uma senha com mais de oito caracteres o vnc irá considerar somente os oito primeiros. 21](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098152)

[5.Descrevendo a instalação do servidor SAMBA 22](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098153)

[5.1 Criar senha para acesso ao Samba 24](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098154)

[5.2 Copiar arquivos do PC para o Raspberry Pi com Filezilla e vice-versa 27](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098155)

6.Conhecendo/revendo os principais comandos Linux para usar no Raspberry Pi 27

[6.1 Listagem de Arquivos e Movimentação 27](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098157)

[6.3 Navegação – Endereços absolutos 28](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098158)

[6.4 Endereço relativo – Descer um nível 30](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098159)

[6.5 Criação de diretórios 30](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098160)

[6.6 Criação de arquivos 31](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098161)

[6.7 Copiar arquivos 31](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098162)

[6.8 Mover e renomear arquivos 31](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098163)

[6.9 Listar e remover processos em execução 32](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098164)

[7.PISCANDO UM LED COM O RASPBERRY utilizando ‘Wiringpi’ 32](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098165)

[7.1 Comandos de entrada e saída no LXTerminal 35](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098166)

[7.2 Resistores internos de pull-up e pull-down 36](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098167)

[7.3 Comandos _shell_ para acionamento dos pinos 37](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098168)

[7.4 Comandos WiringPi 38](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098169)

[8.Modulação por largura de pulso PWM pela biblioteca Wiringpi 41](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098170)

[8.1 Modulação por largura de pulso (PWM) por Hardware 41](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098171)

[9.Comunicação serial entre um microcontrolador PIC e Raspberry Pi 43](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098172)

9.1 Funções seriais WiringPi 44

9.2 Configuração serial do Raspberry Pi 46

9.3 Configurando manualmente a porta serial com minicom 46

[9.4 RTOS em um PIC de 8 bits com conversor A/D e comunicação serial 57](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098176)

[10.Gravando o PIC via USB utilizando RPi 61](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098177)

[11.Tutorial de Instalação da gravação de firmware em nuvem 65](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098178)

[12.Interrupções com wiringPi 65](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098179)

[13.Interrupções e Tarefas concorrentes com wiringPi 67](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098180)

[13.1 PI_THREADS NO LINUX 67](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098181)

[13.1.1Processamento simultâneo (multi-threading) 67](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098182)

[13.2 Funções Auxiliares 71](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098183)

[14.Biblioteca CURL 71](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098184)

[14.1 Exemplos: Acessar um siste para post no LXTerminal 71](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098185)

15.Referências 72

[16.Apêndices 73](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098187)

[16.2Tunelamento SSH 76](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098188)

[16.3 Configurando o WiFi no Raspberry Pi com USB dongle 78](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098189)

[16.4 Raspberry como Servidor 78](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098190)

[16.5 A instalação de um servidor web e transferência de um Website 79](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098191)

[16.6 CURL no PHP 82](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098192)

[16.7 Copiar arquivos do PC para o Raspberry Pi com Filezilla e vice-versa 82](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098193)

[16.8 Dropbox no Raspberry 84](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098194)

[16.8.1 Comandos: 85](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098195)

[16.9 Banco de dados estruturado MySQL 88](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098196)

[16.9.1 Conexão ao MySQL de um servidor online 90](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098197)

[16.9.2 Comando do MySQL 92](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098198)

[16.9.3 Atualizando o Raspberry Pi 93](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098199)

[16.10 Instalando o MySQL Client 94](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098200)

[16.11 Banco de dados estruturado SQlite 99](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098201)

[16.12 Modificar o nome do Rpi 106](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098202)

[16.13 Modificar a senha do Usuário pi 106](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098203)

[16.14 Modificar data, hora e fuso horário do Rpi 106](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098204)

[16.15 Configurar o teclado para uso local 108](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098205)

[16.16 Criar, ler e escrever em um arquivo via Shell 108](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098206)

[16.17 Simulação de Comunicação GPIO Raspberry usando php e mysql com raspian no VirtualBox 112](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098207)

[16.18 Semáforo utilizando pinos GPIO do raspberry pi e MySql 118](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098208)

[16.19 Controle WiFi de Robô móvel (motor CC) pelo Rpi via SSH 122](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098209)

**Índice de Figuras**

Figura 1: Raspberry Pi. 7

Figura 2: Quatro modelos de Raspberry Pi. 9

Figura 3: Tela gerada pelo Raspberry Pi. 11

Figura 4: SD Formatter. 12

Figura 5: Win32DiskImager. 12

Figura 6: Confirmação de gravação da imagem no cartão SD. 13

Figura 7: Win32 Disk Imager. 14

Figura 8: Abrir local do arquivo. 14

Figura 9: Concluir backup. 15

Figura 10: Escrever imagem no cartão SD. 15

Figura 11: Minibian. 18

Figura 12: TightVNC. 20

Figura 13: service samba restart. 23

Figura 14: Arquivos compartilhados na pasta _share_. 24

Figura 15: Acesso ao Rpi. 24

Figura 16: Filezilla. 27

[Figura 17: Localização atual no Rpi. 28](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098372)

[Figura 18: Arquivos locais. 28](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098373)

[Figura 19: Raiz do Rpi. 28](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098374)

[Figura 20: Diretórios Rpi. 29](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098375)

[Figura 21: Diretórios Rpi. 30](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098376)

[Figura 22: Pinos GPIO. 34](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098377)

[Figura 23: Conexão de LED ao Rpi. 34](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098378)

[Figura 24: Pinos GPIO. 34](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098379)

[Figura 25: Conexão de botão ao Rpi. 36](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098380)

[Figura 26: Wiring Pi. 39](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098381)

[Figura 27:Pinos necessários para comunicação serial. 44](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098382)

[Figura 28: Conexão entre o modem bluetooth e o Raspberry Pi. 44](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098383)

[Figura 29: Serial Port Setup. 47](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098384)

[Figura 30: Configurações no LXTerminal. 47](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098385)

[Figura 31: Configurações no LXTerminal. 48](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098386)

[Figura 32: Configurações no LXTerminal. 48](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098387)

[Figura 33: Saindo do minicom. 49](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098388)

[Figura 34: Ilustração da comunicação serial entre Pic e Rpi 49](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098389)

[Figura 35: Prática em funcionamento, recebendo comandos bluetooth e enviando valores do potenciometro para a serial.. 59](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098390)

[Figura 36: Conexão entre Rpi e PIC. 63](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098391)

[Figura 37: Tunelamento SSH. 76](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098392)

[Figura 38: Tunelamento SSH. 77](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098393)

[Figura 39: Filezilla. 83](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098394)

[Tabela 1: Tabela user do MySQL. 89](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098395)

[Figura 40: Database. 93](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098396)

[Figura 41: Tabelas do banco MySQL. 93](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098397)

Figura 42: Tabela exemplo banco de dados. 101

[Figura 43: Tela inicial do projeto para login na ferramenta. 116](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098399)

[Figura 44:Sistema raspbian emulado no Oracle Virtual Box com 512 de memória ram. 117](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098400)

[Figura 45:Pasta www do apache com os arquivos necessários para funcionamento do projeto. 117](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098401)

[Figura 46: Tela principal do projeto, onde pode-se comandar os leds através de botões. 118](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098402)

[Figura 47: Prática em funcionamento com protoboard e raspberry pi 2 conectado à internet. 122](export/minibian_minimal_raspbian.md#641552765388041-_Toc449098403)


