# Configurar o ambiente para programar para Android

## 1. Instalar o Java e o compilador Java na versão 17
```bash
sudo apt install openjdk-17-jdk-headless
```

## 2. Baixar o "cmdline-tools"
Acesse o link abaixo para baixar o pacote:
[Android Developer](https://developer.android.com/studio?hl=pt-br)

## 3. Configurar o "cmdline-tools"
Extraia o conteúdo do arquivo baixado e mova para o diretório correto:
```bash
mkdir -p $HOME/Android/Sdk/cmdline-tools/latest
mv caminho/do/arquivo-extraido/* $HOME/Android/Sdk/cmdline-tools/latest/
```

## 4. Configurar variáveis de ambiente
Adicione as seguintes linhas ao arquivo `~/.bashrc`:
```bash
export ANDROID_HOME=$HOME/Android/Sdk
export ANDROID_SDK_ROOT=$ANDROID_HOME
export PATH=$PATH:/home/$USER/Android/Sdk/cmdline-tools/latest/bin
```

## 5. Atualizar o `~/.bashrc`
```bash
source ~/.bashrc
```

## 6. Instalar as dependências do Android SDK
```bash
sdkmanager --install "platform-tools" "build-tools;34.0.0"
```

---

# Executar projeto React Native

## 1. Criar um novo projeto React Native
```bash
npx @react-native-community/cli init MeuApp
```

## 2. Configurar o SDK no projeto
```bash
echo "sdk.dir=$HOME/Android/Sdk" > android/local.properties
```

## 3. Compilar o projeto
```bash
cd android && ./gradlew assembleRelease
```

