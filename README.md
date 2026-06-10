# Edge-Computing_GS1
# 🛰️ OrbitEye

## 🔥 Sistema Inteligente de Detecção de Queimadas com Arduino

<p align="center">
  <img src="https://img.shields.io/badge/Arduino-Project-blue?style=for-the-badge&logo=arduino">
  <img src="https://img.shields.io/badge/FIAP-Global%20Solution-red?style=for-the-badge">
  <img src="https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge">
</p>

---

# 📌 Sobre o Projeto

O **OrbitEye** é um sistema inteligente de monitoramento e detecção de queimadas desenvolvido com Arduino para a **Global Solution FIAP**.

Inspirado nas tecnologias utilizadas por satélites de observação terrestre, o sistema é capaz de identificar possíveis focos de incêndio através da análise de fumaça e temperatura, emitindo alertas visuais e sonoros em tempo real.

O projeto utiliza conceitos de **Edge Computing**, onde todas as decisões são tomadas localmente pelo Arduino, garantindo respostas rápidas sem depender de conexão com a internet.

---

# 🖼️ Montagem do Circuito

<p align="center">
  <img src="https://github.com/user-attachments/assets/f7e87fc9-f985-4d5f-a00c-f44456381c18" alt="Circuito Arduino OrbitEye" width="700"> 
</p>

<p align="center">
  🔌 Representação do circuito montado no Tinkercad utilizando Arduino Uno, sensor de fumaça, sensor de temperatura, LCD, LEDs e buzzer.
</p>

---

# 🔍 Entendendo a ligação (explicação simples)

* 🔌 **Arduino Uno** → funciona como o cérebro do sistema, controlando todos os componentes.
* 🌫️ **Sensor MQ-2** → detecta fumaça e gases presentes no ambiente.
* 🌡️ **Sensor TMP36** → monitora a temperatura ambiente em tempo real.
* 📟 **Display LCD 16x2** → exibe as informações coletadas pelos sensores.
* 🟢 **LED Verde** → indica que o ambiente está seguro.
* 🔴 **LED Vermelho** → indica situação de alerta.
* 🔊 **Buzzer** → emite um alerta sonoro quando há risco detectado.
* 🧩 **Protoboard** → utilizada para organizar as conexões do circuito.
* 🔗 **Jumpers (fios)** → responsáveis pela comunicação entre os componentes.

---

👉 O funcionamento do sistema acontece da seguinte forma:

1. O sensor MQ-2 monitora constantemente a presença de fumaça.
2. O sensor TMP36 mede continuamente a temperatura ambiente.
3. O Arduino recebe os dados dos sensores.
4. Os valores são processados localmente.
5. Caso seja identificado risco de incêndio:

   * O LED vermelho é acionado;
   * O buzzer dispara um alerta sonoro;
   * Uma mensagem de alerta aparece no LCD.
6. Caso não haja risco:

   * O LED verde permanece ligado;
   * O sistema informa que o ambiente está seguro.

---

# 💡 O que está acontecendo na prática?

1. O sensor MQ-2 verifica a presença de fumaça.
2. O sensor TMP36 monitora a temperatura.
3. O Arduino processa os dados recebidos.
4. O sistema decide automaticamente se existe risco de incêndio.
5. O resultado é exibido no display LCD em tempo real.

---

As queimadas representam um dos maiores desafios ambientais da atualidade, causando destruição de florestas, prejuízos econômicos e impactos climáticos significativos.

Muitas vezes, os focos de incêndio são identificados apenas quando já atingiram grandes proporções.

O OrbitEye busca demonstrar como sistemas inteligentes de monitoramento podem auxiliar na identificação precoce desses eventos.

---

# 🛰️ Relação com a Indústria Espacial

Atualmente, satélites são utilizados para monitorar a superfície terrestre e identificar focos de queimadas em diversas regiões do planeta.

Esses sistemas utilizam sensores capazes de detectar alterações térmicas e sinais associados a incêndios.

O OrbitEye foi inspirado nesse conceito, reproduzindo em escala educacional a lógica utilizada em sistemas de monitoramento espacial.

---

# 🧩 O que cada parte do sistema faz

## 🔌 Arduino Uno (o cérebro)

Recebe todas as informações dos sensores, processa os dados e controla os dispositivos de alerta.

---

## 🌫️ Sensor MQ-2

Detecta:

* Fumaça;
* Gases inflamáveis;
* Alterações na qualidade do ar.

---

## 🌡️ Sensor TMP36

Mede a temperatura ambiente continuamente.

Permite identificar aumentos anormais de temperatura que podem indicar focos de incêndio.

---

## 📟 Display LCD 16x2

Mostra as informações para o usuário:

* Valor da fumaça detectada;
* Temperatura atual;
* Status do sistema.

---

## 🟢 LED Verde

Indica que o ambiente está seguro.

---

## 🔴 LED Vermelho

Indica situação de risco ou possível incêndio.

---

## 🔊 Buzzer

Emite um alerta sonoro para chamar atenção imediatamente.

---

## 🧩 Protoboard

Organiza as conexões sem necessidade de solda.

---

## 🔗 Jumpers

Responsáveis por conectar todos os componentes.

---

# ⚙️ Componentes Utilizados

* 🔌 Arduino Uno
* 🌫️ Sensor MQ-2
* 🌡️ Sensor TMP36
* 📟 Display LCD 16x2
* 🔴 LED Vermelho
* 🟢 LED Verde
* 🔊 Buzzer
* 🔩 Resistores
* 🧩 Protoboard
* 🔗 Jumpers

---

# 🔋 Como o sistema funciona (passo a passo)

## 🥇 1. Monitoramento

O sistema realiza continuamente a leitura:

* Da fumaça através do sensor MQ-2;
* Da temperatura através do sensor TMP36.

---

## 🥈 2. Envio das informações

Os sensores enviam seus dados para o Arduino.

---

## 🥉 3. Análise pelo Arduino

O Arduino compara os valores recebidos com limites definidos no código.

Exemplo:

* Fumaça acima de 300;
* Temperatura acima de 60°C.

---

## 🏁 4. Resposta do sistema

### Ambiente Seguro

```text
F:120 T:28.5C
Ambiente Seguro
```

* LED verde ligado;
* LED vermelho desligado;
* buzzer desligado.

### Situação de Risco

```text
F:450 T:65.2C
ALERTA: INCENDIO
```

* LED vermelho ligado;
* LED verde desligado;
* buzzer ativado.

---

# 🧠 Lógica do Sistema (como o Arduino "pensa")

```cpp
if (valorFumaca > 300 || temperaturaC > 60.0)
{
    digitalWrite(ledVerde, LOW);
    digitalWrite(ledVermelho, HIGH);
    tone(buzzer, 1000);

    lcd.setCursor(0,1);
    lcd.print("ALERTA: INCENDIO");
}
else
{
    digitalWrite(ledVerde, HIGH);
    digitalWrite(ledVermelho, LOW);
    noTone(buzzer);

    lcd.setCursor(0,1);
    lcd.print("Ambiente Seguro ");
}
```

👉 O Arduino utiliza estruturas condicionais simples para tomar decisões automaticamente.

---

# 📊 Exemplo de Funcionamento

| Situação do Ambiente      | O que acontece               |
| ------------------------- | ---------------------------- |
| Ambiente normal           | 🟢 Sistema seguro            |
| Presença de fumaça        | 🔴 Alerta visual             |
| Temperatura elevada       | 🔴 Alerta visual             |
| Fumaça ou calor excessivo | 🔊 Buzzer acionado           |
| Situação crítica          | 📟 Mensagem de alerta no LCD |

---

# 🎯 Objetivos do Projeto

* ✔ Aplicar conceitos de Edge Computing
* ✔ Desenvolver soluções utilizando Arduino
* ✔ Trabalhar com sensores reais
* ✔ Implementar sistemas de monitoramento inteligente
* ✔ Simular aplicações inspiradas na indústria espacial
* ✔ Criar lógica de decisão utilizando programação embarcada
* ✔ Desenvolver uma solução para prevenção de queimadas

---

# 🛠️ Tecnologias Utilizadas

<p>
<img src="https://img.shields.io/badge/Arduino-00979D?style=flat&logo=arduino&logoColor=white">
<img src="https://img.shields.io/badge/Tinkercad-FF6F00?style=flat">
<img src="https://img.shields.io/badge/Edge%20Computing-blue">
<img src="https://img.shields.io/badge/Eletrônica-Básica-green">
</p>

---

# 🔗 Acesse o Projeto

## 👉 Tinkercad

https://www.tinkercad.com/things/jDMz0qF1FJv-edge-sensor-de-fumaca-e-temperatura/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=XIrST02wrIScF1XBvDoWstSeO5T3S04ErnZe-psUqRA

---

## 👉 Youtube
https://youtu.be/72kXCpKjEsQ
---
# 👨‍💻 Integrantes

| Integrante        | RM     |
| ----------------- | ------ |
| Guilherme Gimenez | 563389 |
| Guilherme Canno   | 573183 |
| Luan Garbin       | 571276 |
| Erick Ripari      | 569441 |

---

# 🏫 Contexto Acadêmico

Projeto desenvolvido para a **Global Solution FIAP**, integrando conceitos de Edge Computing, Sistemas Embarcados e Monitoramento Inteligente inspirado em tecnologias utilizadas na indústria espacial para detecção e prevenção de queimadas.
