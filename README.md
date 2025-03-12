# Configurar o ambiente para programar para android

1 - Instalar o java e javac na versão 17:

sudo apt install openjdk-17-jdk-headless


2 - Baixar o "cmdline-tools" em:
https://developer.android.com/studio?hl=pt-br

3 - Jogar o conteúdo de "cmdline-tools" extraído para /home/$USER/Android/Sdk/
Criar uma pasta dentro de "/home/$USER/Android/Sdk/cmdline-tools" chamada "latest" e mover o contúdo da pasta para "latest".

4 - Configurar variáveis de ambiente em ~/.bashrc:

export ANDROID_HOME=$HOME/Android/Sdk
export ANDROID_SDK_ROOT=$ANDROID_HOME
export PATH=$PATH:/home/$USER/Android/Sdk/cmdline-tools/latest/bin


5 - Atualizar o ~/.bashrc:
source ~/.bashrc

Instalar as dependências:

sdkmanager --install "platform-tools" "build-tools;34.0.0"

# --------------------------------------------------

# Executar projeto react-native:

npx @react-native-community/cli init MeuApp
echo "sdk.dir=$HOME/Android/Sdk" > android/local.properties
cd android && ./gradlew assembleRelease
