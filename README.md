# sismolog-a.py
from obspy import read

def procesar_sismograma(archivo, freq_min, freq_max):
    # Leer archivo de datos sismológicos
    stream = read(archivo)
    print("Detalles del archivo:")
    print(stream)

print("Detalles del archivo:")
print(stream)

# Graficando la señal original
print("\nGraficando la señal original...")
stream.plot()

# Aplicar un filtro pasa-bajos con una frecuencia de corte de 1 Hz
print("\nAplicando filtro pasa-bajos...")
stream_filtrada = stream.copy()
stream_filtrada.filter("lowpass", freq=1.0)

# Graficando la señal filtrada
print("\nGraficando la señal filtrada...")
stream_filtrada.plot()
