# BookMatch-AI
Sistema de recomendación de libros con IA
Proyecto: BookMatch - Recomendador de Libros con IA
(Final project for the Building AI course)

🔍 Resumen (Summary)
BookMatch es un sistema de recomendación de libros que usa IA para sugerir lecturas basadas en los gustos del usuario, reseñas y similitudes con otros lectores. ¡Nunca más preguntarás "¿Qué libro leer?"!

📚 Fondo (Background)
Problema que resuelve:

Muchos lectores pierden tiempo buscando libros que se ajusten a sus preferencias.

Los algoritmos tradicionales (como "los más vendidos") no son personalizados.

Motivación personal:

Soy un ávido lector y sé lo frustrante que es elegir un libro mal recomendado.

La IA puede analizar patrones complejos (género, autor, rating) para hacer sugerencias precisas.

Importancia:

El mercado global de libros supera los $143 mil millones (Statista, 2023).

Soluciones como Goodreads existen, pero no usan IA avanzada para personalizar recomendaciones.

📊 Datos y Técnicas de IA
Fuentes de datos:

Dataset público de Goodreads (10,000 libros con ratings, géneros y autores).

API de Google Books para información adicional.

Técnicas de IA:

Filtrado colaborativo: Compara tus gustos con otros usuarios similares.

Procesamiento de Lenguaje Natural (NLP): Analiza reseñas para extraer temas clave.

Modelo híbrido: Combina filtrado colaborativo + NLP para mayor precisión.



# Ejemplo simplificado en Python
from sklearn.neighbors import NearestNeighbors
import pandas as pd

# Cargar datos (ejemplo)
data = pd.read_csv('goodreads_data.csv')
model = NearestNeighbors(n_neighbors=5).fit(data[['rating', 'genre_encoded']])

# Recomendar libros similares
user_preferences = [4.5, 7]  # Rating alto, género "Ciencia Ficción"
distances, indices = model.kneighbors([user_preferences])
print("Libros recomendados:", data.iloc[indices[0]]['title'])
