# RP2040-PiZero

Adaptación del Multicore por HDMI/spi-tft ALMA de Guillermo Amat a la placa RP2040 con 16Mbytes de SPIFLASH de la marca WAVESHARE.
Se ha escogido esta placa dado que trae todos los puertos necesarios y aquí se discutirán los cambios a realizar.

Posición del marco de trabajo así como el multicore y la primera versión de caja 3D, asociada al modelo I/O Board ATLAS V002 sin puerto de carga de casete "EAR".

https://gitlab.com/fpga-boards

Información de donde están colocados los ficheros cabeceras para adaptar desde el diseño de Guillermo  Amat, y migrarlo a la RP2040-PiZero.										
Ruta de las señales asociadas al bus de programación y depurado JTAG:	

ALMA-FIRMWARE-MASTER -> src -> jtag.h										

          
| definicion |Nombre variables	| Valores	Guillermo AMAT| Valores		RP2040-PiZero|	
| ----- | ---- |----- | ---- |
|#define 	|PIN_TCK |	2     |		17	 |				
|#define 	|PIN_TDI |	4	    |	  22	 |		
|#define 	|PIN_TMS |	5     |		14	 |			
|#define 	|PIN_TDO | 	3     |		27	 |			
|#define 	|WRITEPIN|gpio_put|		     |						
										
										
Ruta asociada a las señales de la micro sd incorporada en la RP2040-PiZero:	

ALMA-FIRMWARE-MASTER ->  src -> configuration -> pico -> ST7735 ->User_Setup.h										
										
|definicion|Nombre variables	|Valores	Guillermo AMAT| Valores		RP2040-PiZero| explicación señal|	
| ----- | ---- |----- |----- | ---- |
|#define 	 |TFT_SCLK	| 10	|	18				| //18//PIN_SPI_SCK //14                           |		
|#define 	 |TFT_MOSI	| 11	|	19				| //19//PIN_SPI_MOSI//15                           |		
|#define 	 |TFT_MISO	| 12	|	20				| //16//PIN_SPI_MISO//10                           |		
|#define 	 |TFT_DC	  | 7   |						| // Reset pin (could connect to RST pin)          |		
|#define 	 |TFT_RST	  | 8   |						| //17//PIN_SPI_SS //13 // Chip select control pin |		
|#define 	 |TFT_CS	  | 9	  |	21        |                                                  |						

Pueden consultar los valores asociados a la RP2040-Pizero de wavesare de una forma más visual en el siguiente enlace de google documentos.

https://docs.google.com/spreadsheets/d/1McALQf85XnruqYqf6eDq89t5m_BvRBwcVS2hHGKuhcs/edit?usp=sharing

Foto de la combinación de las 3 placas,TRENZ CYC1000, WAVESHARE RP2040-PiZero con la I/O Board ATLAS:

Montaje último prototipo:

![Montaje último prototipo](https://github.com/AtlasFPGA/RP2040-PiZero/blob/main/FOTOS/Ultimo_prototipo_RP2040VIDEO.JPG)

