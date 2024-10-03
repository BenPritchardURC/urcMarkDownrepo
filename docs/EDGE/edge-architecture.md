## EDGE Architecture

``` mermaid
graph 
  B[H755 Protection Firmware] --> |SPI| C[M4 Realtime Firmware]
    C --> |OpenAMP| D[A7-OpenSTLinux]
    D --> E[stm32_main]
    E --> stm32-golang-http-server
    E --> stm32_QT5

 ```