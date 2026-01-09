# ROS 2 Publisher & Subscriber – Sinal Senoidal (Python)

Projeto em ROS 2 utilizando Python (`rclpy`) que demonstra comunicação **publisher–subscriber** por meio da publicação e recepção de um **sinal senoidal**.

---

## Objetivo

- Implementar um **nó publisher** que publica uma onda senoidal 
- Implementar um **nó subscriber** que recebe e processa os dados 
- Praticar comunicação entre nós em ROS 2 
- Visualizar dados publicados em tempo real 

---

## Estrutura do Pacote

```
pubsub_py/
├── pubsub_py/
│   ├── sine_wave_pub.py      # Nó publisher
│   ├── sine_wave_sub.py      # Nó subscriber
│   └── __init__.py
├── package.xml
├── setup.py
├── setup.cfg
├── resource/
└── test/
```

---

## Nó Publisher – Sinal Senoidal

O nó publisher:
- Publica mensagens do tipo `Float64`
- Gera uma **onda senoidal**
- Utiliza `create_timer` para publicação periódica

O valor do seno é calculado em função do tempo e publicado em um tópico ROS 2.

---

## Nó Subscriber – Recepção do Sinal

O nó subscriber:
- Assina o tópico do sinal senoidal
- Recebe os valores publicados
- Processa os dados via callback

---

## Recebendo e Plotando o Sinal Senoidal

O subscriber:
- Armazena os valores recebidos
- Utiliza a biblioteca `matplotlib` para gerar um gráfico do sinal
- Pode empregar **threading** para evitar bloqueio da execução do ROS 2

Essa abordagem permite visualizar o comportamento do sinal senoidal ao longo do tempo.

---

## Comandos Úteis

```bash
ros2 node list
ros2 topic echo /sine_wave
ros2 topic hz /sine_wave
```

---

## Execução

```bash
colcon build
source install/setup.bash
ros2 run pubsub_py sine_wave_pub
ros2 run pubsub_py sine_wave_sub
```

---

## Tecnologias

- ROS 2 Humble
- Python 3
- rclpy
- std_msgs
- matplotlib
- colcon
- Docker
