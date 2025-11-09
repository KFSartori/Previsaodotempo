# WeatherApp Projeto Prático - Previsão do Tempo

Este repositório contém um esqueleto de projeto Android que atende aos requisitos da Atividade Prática Orientada da disciplina de Programação de Dispositivos Móveis. O objetivo é servir como base para a implementação de um aplicativo de previsão do tempo utilizando **Java**.

## Funcionalidades previstas

- Tela de **Splash** que exibe uma imagem por alguns segundos antes de abrir a tela principal.
- Tela principal com **barra de navegação** e duas **abas**:
  - **Previsão**: Fragmento contendo uma lista (RecyclerView) das previsões diárias obtidas via API. Há um botão flutuante para alterar a cidade via leitura de QR Code (não implementado neste esqueleto).
  - **Mapa**: Fragmento exibindo um mapa do Google com um marcador fixo na cidade da previsão.
- Menu na **AppBar** com item “Sobre”, que abre uma nova activity contendo informações pessoais do aluno.

## Estrutura do projeto

```
weather_app/
├── app/
│   ├── build.gradle          # Configurações do módulo de app
│   ├── src/main/
│   │   ├── java/com/example/weatherapp/
│   │   │   ├── AboutActivity.java
│   │   │   ├── MainActivity.java
│   │   │   ├── SplashActivity.java
│   │   │   ├── WeatherFragment.java
│   │   │   ├── MapFragment.java
│   │   │   ├── SectionsPagerAdapter.java
│   │   │   ├── WeatherService.java
│   │   │   ├── WeatherResponse.java
│   │   │   ├── Results.java
│   │   │   ├── Forecast.java
│   │   │   └── WeatherAdapter.java
│   │   ├── res/
│   │   │   ├── layout/
│   │   │   │   ├── activity_splash.xml
│   │   │   │   ├── activity_main.xml
│   │   │   │   ├── activity_about.xml
│   │   │   │   ├── fragment_weather.xml
│   │   │   │   ├── fragment_map.xml
│   │   │   │   └── item_weather.xml
│   │   │   ├── drawable/
│   │   │   │   └── ic_qr_code.xml
│   │   │   ├── menu/
│   │   │   │   └── menu_main.xml
│   │   │   └── values/
│   │   │       ├── strings.xml
│   │   │       ├── colors.xml
│   │   │       └── themes.xml
│   └── proguard-rules.pro
├── build.gradle                # Configuração raiz do Gradle
└── settings.gradle             # Declaração dos módulos
```

## Como utilizar

1. **Importar no Android Studio**: Abra o Android Studio e selecione `Open an Existing Project`. Navegue até o diretório `weather_app` e importe.
2. **Adicionar chave da API do HG Brasil**: No arquivo `WeatherFragment.java`, substitua `YOUR_HGBRASIL_KEY` pela sua chave obtida em [https://console.hgbrasil.com/documentation/weather](https://console.hgbrasil.com/documentation/weather). A cidade padrão é Cascavel/PR, mas poderá ser alterada dinamicamente através do QR Code.
3. **Adicionar chave do Google Maps**: No arquivo `AndroidManifest.xml`, substitua `YOUR_API_KEY_HERE` pela chave de API do Google Maps obtida no Google Cloud. Siga as instruções oficiais para gerar uma chave e habilitar o SDK de mapas.
4. **Implementar leitura de QR Code**: O botão flutuante (`FloatingActionButton`) presente no `fragment_weather.xml` foi configurado para disparar um `Toast`. Para implementar a leitura de QR Code com a biblioteca ZXing, consulte a documentação em [https://github.com/journeyapps/zxing-android-embedded](https://github.com/journeyapps/zxing-android-embedded). A ideia é capturar o conteúdo do QR Code e usar como nova cidade a ser consultada.
5. **Personalizar a tela de Sobre**: No arquivo `activity_about.xml`, atualize os textos com seu nome, RA e curso. Você também pode adicionar sua foto substituindo o ícone de perfil.
6. **Commits frequentes**: Crie um repositório no GitHub, inicialize um repositório local, faça commits conforme avança e envie para o GitHub com `git push`. Inclua este README.md atualizado explicando como executar e qualquer configuração adicional.

## Licença
Este projeto é fornecido como um exemplo educacional para a Atividade Prática Orientada da disciplina de Programação de Dispositivos Móveis e pode ser modificado livremente pelos alunos para fins acadêmicos.