# Instalação do Docker no Windows

A instalação do Docker no Windows requer algumas etapas. Siga as instruções abaixo para instalar e configurar corretamente

## Pré-requisitos
* Windows 10, versão 1903 ou superior, com a Build 18362 ou superior
* Processador com suporte a virtualização habilitada na BIOS
* Hyper-V habilitado
* WSL 2 ativado

## Instruções

1. Abra o PowerShell como administrador e digite os seguintes comandos na ordem apresentada:
 
``` powershell
wsl --update 

dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart 

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart 

wsl --set-default-version 2 
```

2. Habilite o Hyper-V, reinicie o computador e verifique se ele está ativado. Para isso, abra o Painel de Controle, selecione "Programas" e, em seguida, "Ativar ou desativar recursos do Windows". Marque a opção "Hyper-V" e clique em "OK".

![Ativação hyper-v](./assets/images/hyper-v.png)

3. Para ativar a virtualização em seu computador, você precisa acessar a BIOS. Se você tiver um processador AMD, procure pela opção SVM e ative-a. Se você tiver um processador Intel, procure pela opção VT-x e ative-a. A ativação da virtualização permitirá que você use recursos importantes, como máquinas virtuais, em seu sistema. Por favor, siga cuidadosamente as instruções do fabricante para acessar a BIOS e ativar a virtualização.

![Ativação hyper-v](./assets/images/virtualizacao.png)

4. Faça o download do Docker Desktop em [download](https://www.docker.com/get-started)

5. Após a instalação, abra o Docker Desktop e verifique se ele está em execução digitando o seguinte comando no terminal:

``` shell
$ docker ps
```

![Teste Docker](./assets/images/docker-ps.png)

6. Se ocorrer algum problema, tente desabilitar "Use the WSL 2 based engine" nas configurações do Docker Desktop.
    ![Ativação hyper-v](./assets/images/disable-wsl2.png)

Seguindo essas instruções, você deverá conseguir instalar e executar o Docker no Windows sem problemas.
  
