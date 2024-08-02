
# PokerGPT - Bot de poker con GPT-4 para Pokerstars

PokerGPT es un avanzado bot de poker en línea para Pokerstars (juego de efectivo de Texas Hold'em para 6 jugadores) que utiliza la API de OpenAI GPT-4 para el análisis en tiempo real del estado del juego y la toma de decisiones. Cuenta con una interfaz gráfica de usuario integrada para visualizar los datos del poker y soporte de voz para reproducir acciones en la mesa.

![PokerGPT_GUI](https://github.com/HarperJonesGPT/PokerGPT/assets/154810617/8310109b-5086-470b-92ba-81854f132cb2)

## Características

- Detección en tiempo real de eventos del juego leyendo píxeles en la pantalla.
- Utiliza la API OCR de Tesseract para reconocer cartas, tamaños del bote, botón del crupier y todas las acciones de los jugadores.
- Usa 'gpt-4-1106-preview' para analizar los datos del juego y los jugadores con el fin de tomar la acción apropiada (retirarse, pasar, subir, apostar, etc.).
- Ingeniería avanzada de prompts de GPT-4 para analizar estados del juego, explotación de jugadores y creación de estrategias.
- Simula clics del ratón dentro del cliente de Pokerstars para el juego automatizado.

## Requisitos previos

- Python 3.8 o superior
- Acceso a la API de OpenAI GPT-4
- OCR de Tesseract para el reconocimiento de texto
- Cliente de Pokerstars

## Instalación

1. Clona el repositorio en tu máquina local.
2. Instala las dependencias de Python requeridas ejecutando `pip install -r requirements.txt`.
3. Configura tu clave de API de OpenAI en el archivo `pokergpt.env`. (regístrate para obtener una cuenta gratuita en https://openai.com/ y obtén tu clave de API aquí: https://platform.openai.com/api-keys)
4. Asegúrate de que OCR de Tesseract esté instalado y su ruta esté configurada correctamente en los scripts (Tesseract está incluido y la ruta está configurada).

## Configuración del cliente de PokerStars (Visual):

1. Como este bot lee todos los datos de la ventana del cliente de poker, necesitarás configurar los visuales exactamente como en esta imagen:
2. Desactiva todas las animaciones para el cliente de Pokerstars en la configuración de la mesa.
![PokerTable2](https://github.com/HarperJonesGPT/PokerGPT/assets/154810617/ba0a7bc5-d2d1-4237-bfd8-015ca2ca14e9)

## Uso

Para iniciar PokerGPT, sigue estos pasos:

1. Abre el cliente de Pokerstars y asegúrate de que sea visible en la pantalla.
2. Ejecuta `main.py` para iniciar el bot: `python main.py`.
3. Ingresa tu número de jugador (los números de jugador comienzan desde la parte inferior de la mesa y van en sentido horario: 1 (abajo), 2 (abajo-izquierda), 3 (arriba-izquierda), 4 (arriba), 5 (arriba-derecha), 6 (abajo-derecha)).
4. El bot localizará automáticamente la ventana de poker y comenzará a jugar basándose en el análisis de estrategia de GPT-4.

## Estructura

- `audio_player.py`: Maneja la retroalimentación de audio del bot.
- `game_state.py`: Administra el estado actual del juego.
- `gui.py`: Proporciona una interfaz gráfica para monitorear las acciones del bot.
- `hero_action.py`: Contiene la lógica para determinar las acciones del héroe.
- `hero_hand_range.py`: Evalúa los rangos de manos del héroe.
- `hero_info.py`: Recopila información sobre el estado actual del héroe.
- `main.py`: Punto de entrada para ejecutar el bot.
- `poker_assistant.py`: Interactúa con la API de OpenAI para analizar el estado del juego y decidir las acciones.
- `read_poker_table.py`: Utiliza OCR y detección de píxeles para leer el estado de la mesa.

## Limitaciones

- Dependiente del tamaño de la ventana del cliente de Pokerstars (PokerGPT cambia automáticamente a una ventana pequeña).
- Puede que no funcione en todas las resoluciones de pantalla (probado en resolución de pantalla de '1920 x 1080' píxeles, Windows 11).
- Funciona solo en mesas de 6 jugadores de Pokerstars.
- La velocidad de lectura de imágenes (OCR) depende de tu CPU.

## Contribuciones

¡Las contribuciones a PokerGPT son bienvenidas!

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Consulta el archivo `LICENSE.md` para más detalles.

## Soporte

No ofrezco soporte adicional para este proyecto. Si no puedes entenderlo, no es para ti.
